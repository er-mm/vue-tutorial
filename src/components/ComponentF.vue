<template>
    <div id="f">
        <h2>Component F</h2>
        <h3>Component F username - {{username}}</h3>
    </div>
</template>

<script>
    export default {
        name: "ComponentE",
        inject: ['username']
    }
</script>

<style scoped>
#f {
        border: 1px solid black;
        margin: 5px
    }
</style>