<template>
    <div>
        <input type="text" placeholder="firstname" v-model="fname">
        <input type="text" placeholder="last name" v-model="lname">
        <h2>Options Full name is - {{fullName}}</h2>

       <input type="text" placeholder="firstname" v-model="f">
        <input type="text" placeholder="last name" v-model="l">
        <h2>Composition = full nAme is -- {{refFullName}}</h2>

        <input type="text" placeholder="firstname" v-model="rF">
        <input type="text" placeholder="last name" v-model="rL">
        <h2>Computed Reactive full name - {{reactiveFullName}}</h2>
        
    </div>
</template>

<script>
import {ref, computed, reactive, toRefs} from 'vue'
    export default {
        name: 'Computed',
        setup() {
            const f = ref('');
            const l = ref('')

            const refFullName = computed(function() {
                return `${f.value} ${l.value}`
            })

            const state = reactive({
                rF: '',
                rL: ''
            })
            const reactiveFullName = computed(function() {
                return `${state.rF} ${state.rL}`
            })
            return {
                f,l,
                refFullName,
                reactiveFullName,
                ...toRefs(state)
            }
        },
        data() {
            return {
                fname: '',
                lname: ''
            }
        },
        computed: {
            fullName() {
                return `${this.fname} ${this.lname}`
            }
        }
    }
</script>

<style scoped>

</style>