<template>
  <div>
    <h3>Parent Component {{ name }}</h3>
    <h3>Parent Component {{ count }}</h3>
    <h3>Parent Component {{ first }} {{last}}</h3>

    <button @click="increment">Increment count</button>
    <ChildA />
  </div>
</template>

<script>
import { provide, ref, reactive, toRefs } from "vue";
import ChildA from "./ChildA.vue";
export default {
  name: "ProvideInject",
  components: {
    ChildA,
  },
  setup() {
    provide("c_userName", "some value");

    const count = ref(0)
    function increment() {
        count.value++
    }
    const state = reactive({
        first: 'MM',
        lase: 'PM'
    })
    provide("c_count", count);
    provide("c_hero", state);
    provide('inc', increment)

    return {
        count, 
        increment,
        ...toRefs(state)
    }
  },
  data() {
    return {
      name: "Mayank",
    };
  },
  provide() {
    return {
      userName: this.name,
    };
  },
};
</script>

<style scoped>
</style>