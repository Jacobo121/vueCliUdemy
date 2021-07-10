<template lang="">
    <div>
        <h2>Tipo de cuenta: {{cuenta}} </h2>
        <h2>Saldo: {{saldo}}  </h2>
        <h2>Cuenta {{estado ? 'Activa' : 'Desactivada' }} </h2>
        <div v-for="(item, index) in servicios" :key="index">
            {{index + 1 }} - {{ item }}
        </div>
    </div>
</template>
<script>

export default {
    data() {
        return {
            saldo: 1000,
            cuenta: 'visa',
            estado: true,
            servicios: ['giro', 'abono', 'transferencia']
        }
    },
}

</script>
<style lang="">
    
</style>