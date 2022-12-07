<template>
    <div>
        <!-- options api -->
        <input type="text" placeholder="First" v-model="first">
        <input type="text" placeholder="Last" v-model="last">
       
        <input type="text" placeholder="Hero" v-model="heroname">
        <input type="text" placeholder="FirstName" v-model="fName">
        <input type="text" placeholder="LastName" v-model="lName">
    </div>
</template>

<script>
import { ref, reactive, toRefs} from 'vue'
    export default {
        name: 'VModel',
        setup() {
            const heroname = ref("")
            const state = reactive({
                fName: '',
                lName: ''
            })
            return {
                heroname,
                ...toRefs(state)
            }
        },
        data() {
            return {
                first: '',
                last: ''
            }
        }
    }
</script>

<style scoped>

</style>