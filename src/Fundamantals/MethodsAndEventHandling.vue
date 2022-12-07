<template>
    <div>
        <h2>Add Method = {{ add(2,3,4) }}</h2>
        <h2>Multiply Method = {{ multiply(11) }}</h2>
        <h2>{{name}}</h2>
        <div>
            <button @click="name = 'Batman'">Change Name</button>
            <button @mouseover="changeName($event), increment(1, $event)">Change Name</button>
        </div>
            <h2>{{count}}</h2>
        <div>
            <button @click="increment(1, $event)">Increment1</button>
            <button @click="increment(5)">Increment5</button>
            <button @click="decrement(1)">Decrement1</button>
            <button @click="decrement(5)">Decrement5</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'MethodsAndEventHandling',
    data() {
        return {
            baseMultiplier: 5,
            name: 'Mayank',
            count: 0
        }
    },
    methods: {
        add(a,b,c) {
            return a+b+c
        },
        multiply(num) {
            return num*this.baseMultiplier
        },
        increment(num, event) {
            console.log(event)
            this.count += num
        },
        decrement(num) {
            this.count -= num
        },
        changeName(event) {
            console.log(event)
            this.name = "Hello World"
        }
    },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>