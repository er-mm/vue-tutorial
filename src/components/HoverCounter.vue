<template>
    <div>
        <h2 @mouseover="incrementCount">Hovered {{count}} times.</h2>
    </div>
</template>

<script>
// import CounterMixin from '../mixins/Counter'
import useCounter from '../composables/useCounter'

    export default {
        name: 'HoverCounter',
        // mixins: [CounterMixin]
        setup() {
            const {count, incrementCount} = useCounter()

            return {count, incrementCount}
        }
    }
</script>

<style scoped>

</style>