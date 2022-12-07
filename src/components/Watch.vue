<template>
    <div>
        <input type="text" placeholder="Name" v-model="name" />
        
        <input type="text" placeholder="fName" v-model="fName" />
        <input type="text" placeholder="lName" v-model="lName" />


        <input type="text" placeholder="reactive first" v-model="first" />
        <input type="text" placeholder="reactive last" v-model="last" />
        <input type="text" placeholder="reactive heroName" v-model="options.heroName" />
    </div>
</template>

<script>
import {ref, watch, reactive, toRefs} from 'vue'
import _ from 'lodash'
    export default {
        name:'Watch',
        setup() {
            const fName = ref('')
            const lName = ref('Wayne')

            watch([fName, lName], (nVals, oVals) => {
                console.log(nVals, oVals)
            }, {
                immediate: true
            })

            const state = reactive({
                first: '',
                last: '',
                options: {
                    heroName: ''
                }
            })
            // in reactive, old and new values are same
            // to get the old value, we need to make a function and destruct tha state

            // watch(() => {
            //     return {...state}
            // }, function(newVal, oldVal){
            //     console.log(newVal, oldVal)
            // })

            // limitation: if we have 10 watchers, the the callback function will run for every watcher if we change 1 watch. 
            // to resolve that following needs to be done. 

            watch(() => state.first, function(newVal, oldVal) {
                console.log(newVal, oldVal)
            })

            // deep watchers
            watch(() => _.cloneDeep(state.options), function(newVal, oldVal) {
                console.log(newVal, oldVal)
            }, {
                deep: true
            })

            
            return {
                fName,
                lName,
                ...toRefs(state)
            }
        },
        data() {
            return {
                name: ''
            }
        },
        watch: {
            name(newVal, oldVal) {
                console.log(newVal,oldVal)
            }
        }
    }
</script>

<style scoped>

</style>