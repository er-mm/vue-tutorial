<template>
    <div>
        <input type="text" v-model="first">
        <input type="text" v-model="last">
        <PersonGreeting :firstN="first" :lastN="last" @callHeros="callHeros"/>
    </div>
</template>

<script>
import {ref} from 'vue'
import PersonGreeting from './PersonGreeting.vue'
    export default {
        name: 'Person',
        components: {PersonGreeting},
        setup() {
            const first = ref('')
            const last = ref('')

            function callHeros(hero) {
                alert(`calling ${hero}`)
            }
            return {
                first, last, callHeros
            }
        }
    }
</script>

<style scoped>

</style>