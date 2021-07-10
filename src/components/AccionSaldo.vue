<template lang="">
    <div>
        <button :disabled="desactivar" @click="accion" > {{texto}} </button>
    </div>
</template>
<script>
export default {
    props: {
        texto: String,
        desactivar: {
            type: Boolean,
            default: false
        }
    },

    methods: {
        accion() {
            this.$emit('accion')
        },

        
    }
}
</script>
<style lang="">
    
</style>