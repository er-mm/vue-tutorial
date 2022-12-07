<template>
    <div>
        Tab C content
       <div><input type="text" v-model="name"></div>
    </div>
</template>

<script>
    export default {
        name: 'TabC',
        data() {
            return {
                name: ''
            }
        }
    }
</script>

<style scoped>

</style>