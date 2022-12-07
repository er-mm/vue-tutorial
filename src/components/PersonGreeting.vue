<template>
    <div>
        <h2>{{fullName}}</h2>
        <button @click="sendEvent">Calll heros</button>
    </div>
</template>

<script>
import { computed } from 'vue'
    export default {
        name: 'PersonGreeting',
        props: ['firstN', 'lastN'],
        setup(props, context) {
            const fullName = computed(() => {
                return `${props.firstN} ${props.lastN}`
            })

            function sendEvent() {
                context.emit('callHeros', fullName.value)
            }

            return {
                fullName,
                sendEvent
            }
        }
        // computed:{
        //     fullName() {
        //         return `${this.firstN} ${this.lastN}`
        //     }
        // }
    }
</script>

<style scoped>

</style>