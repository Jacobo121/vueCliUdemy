<template lang="">
    <div>
        <h2>Tipo de cuenta: {{cuenta}} </h2>
        <h2>Saldo: {{saldo}}  </h2>
        <h2>Cuenta {{estado ? 'Activa' : 'Desactivada' }} </h2>
        <div v-for="(item, index) in servicios" :key="index">
            {{index + 1 }} - {{ item }}
        </div>
        <AccionSaldo 
            @accion="disminuir" :desactivar="desactivar" texto="Disminuir Saldo" 
        />
        <AccionSaldo 
            @accion="aumentar" texto="Aumentar Saldo" 
        />
    </div>
</template>
<script>
import AccionSaldo from './AccionSaldo.vue'

export default {
    name: "Cuenta",
    components: {
        AccionSaldo
    },
    data() {
        return {
            saldo: 400,
            cuenta: 'visa',
            estado: true,
            servicios: ['giro', 'abono', 'transferencia'],
            desactivar: false
        }
    },

    methods: {
        aumentar() {
            this.saldo = this.saldo + 100
            this.desactivar = false
        },
        disminuir() {
            if(this.saldo === 0) {
                alert("te quedaste sin saldo, no te preocupes")
                this.desactivar = true
                return
            }
            this.saldo = this.saldo - 100
        }
    },
}

</script>
<style lang="">
    
</style>