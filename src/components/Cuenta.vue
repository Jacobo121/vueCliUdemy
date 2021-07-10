<template lang="">
    <div>
        <h2>Tipo de cuenta: {{cuenta}} </h2>
        <h2>Saldo: {{saldo}}  </h2>
        <h2>Cuenta {{estado ? 'Activa' : 'Desactivada' }} </h2>
        <div v-for="(item, index) in servicios" :key="index">
            {{index + 1 }} - {{ item }}
        </div>
        <AccionSaldo @click="disminuir" texto="Disminuir Saldo" />
        <AccionSaldo @click="aumentar" texto="Aumentar Saldo" />
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
            saldo: 1000,
            cuenta: 'visa',
            estado: true,
            servicios: ['giro', 'abono', 'transferencia']
        }
    },

    methods: {
        aumentar() {
            this.saldo = this.saldo + 100
        },
        disminuir() {
            this.saldo = this.saldo - 100
        }
    },
}

</script>
<style lang="">
    
</style>