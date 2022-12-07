<template>
    <div>
        <h2>{{first}} {{last}}</h2>
    </div>
</template>

<script>
import { reactive, toRefs } from 'vue'
    export default {
        name: 'Demo2',
        setup() {
            const state = reactive({
                first: 'Mayank',
                last: 'Mittal'
            })
            setTimeout(() => {
                state.first = "Priyanka",
                state.last = "M"
            }, 2000)
            return toRefs(state)
        }
    }
</script>

<style scoped>

</style>