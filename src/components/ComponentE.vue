<template>
    <div id="e">
        <h2>Component E</h2>
        <ComponentF />
    </div>
</template>

<script>
    import ComponentF from './ComponentF.vue'
    export default {
        name: "ComponentE",
        components: {
            ComponentF
        }
    }
</script>

<style scoped>
#e {
        border: 1px solid black;
        margin: 5px
    }
</style>