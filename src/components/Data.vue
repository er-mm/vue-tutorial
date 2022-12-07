<template>
    <div>
        <h2>Options - {{o_firstName}}</h2>
        <h2>Options - {{o_firstName}} {{o_lastName}} aka {{o_heroName}}</h2>
        <h2>Composition - {{c_firstName}}</h2>
        <h2>Composition - {{greet}}</h2>
        <h2>Composition - {{greetHero}}</h2>
        <h2>Reactive {{state.fName}} {{state.last}} aka {{state.hero}}</h2>
        <h2>reactive - {{reactiveGreetHero}}</h2>
    </div>
</template>

<script>
import { ref, reactive } from 'vue'
    export default {
        name: "Data",
        setup() { 
            const c_firstName = ref('Clark')
            const c_lastName = ref('Kent')
            const c_heroName = ref('Superman')
            // c_firstName.value = 'Diana'
            const greet = `Hello ${c_firstName.value}`
            const greetHero = `Hello ${c_firstName.value} ${c_lastName.value} aka ${c_heroName.value}`
            console.log('c_firstName', c_firstName)

            const state = reactive({
                fName: 'Princess',
                last: 'Diana',
                hero: 'Wonder Women'
            })

            const reactiveGreetHero = `Hello ${state.fName} ${state.last} aka ${state.hero}`
            return {
                c_firstName,
                greet,
                greetHero,
                reactiveGreetHero,
                state
            }
        },
        data() {
            return {
                o_firstName: "Bruce",
                o_lastName: 'Wayne',
                o_heroName: 'Batman'
            }
        }
    }
</script>

<style scoped>

</style>