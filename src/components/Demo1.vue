<template>
    <div>
        <h2>{{name}}</h2>
    </div>
</template>

<script>
import { ref } from 'vue';
    export default {
        name: 'Demo1',
        setup() {
            const name = ref('Mayank')
            setTimeout(() => {
                name.value = "codeEvolution"
            }, 2000)
            return {
                name
            }
        }
    }
</script>

<style scoped>

</style>