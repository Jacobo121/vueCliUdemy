<template>
    <div>
        <h1>{{texto}}</h1>
    </div>
</template>

<script>
export default {
    name: 'Titulo',
    props: {
        texto: String,
    }
}

</script>

<style scoped>
    /*scoped hace que los estilos que pongamos aqui, solo afecten al componente  */
    h1 {
        color: peru;
    }
</style>