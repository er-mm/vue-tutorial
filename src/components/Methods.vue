<template>
    <div>
        <h2>{{ name }}</h2>
        <button @click="setName">Change Name</button>

        <h2>{{count}}</h2>
        <button @click="incrementCount">Increment Count</button>

        <h2>{{first}} {{last}}</h2>
        <button @click="changeHero">Change hero</button>
    </div>
</template>

<script>
import {ref, reactive, toRefs} from 'vue'
    export default {
        name: 'Methods',
        setup() {
            const count = ref(0)

            function incrementCount() {
                count.value++
            }

            const state = reactive({
                first: 'Bruce',
                last: 'Name'
            })

            function changeHero() {
                state.first = "clark",
                state.last = "Kent"
            }
            return {
                count,
                incrementCount,
                changeHero,
                ...toRefs(state)
            }
        },
        data() {
            return {
                name: 'Mayank'
            }
        }, 
        methods: {
            setName() {
                this.name = "Priyanka"
            }
        }
    }
</script>

<style scoped>

</style>