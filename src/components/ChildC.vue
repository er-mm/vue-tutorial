<template>
    <div>
        <h2>Child Component C</h2>
        <h3>Child Component C username - {{userName}}</h3>

        <h3>Child Component C composition username - {{childUserName}}</h3>
        <h3>Child Component C composition count - {{childCount}}</h3>
        <h3>Child Component C composition hero - {{first}} {{last}}</h3>
        <button @click="incrementCount">Increment count from child</button>
    </div>
</template>

<script>

import {inject, toRefs} from 'vue'
    export default {
        name: 'ChildC',
        setup() {
            const childUserName = inject('c_userName', 'default username')
            const childCount = inject('c_count', 0)
            const childHero = inject('c_hero', {})
            const incrementCount = inject('inc')
            return {
                childUserName, 
                childCount,
                incrementCount,
                ...toRefs(childHero)
            }
        },
        inject: ['userName']
    }
</script>

<style scoped>

</style>