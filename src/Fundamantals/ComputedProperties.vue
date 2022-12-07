<template>
    <div>
        <h2>Full Name - {{firstName}} {{lastName}}</h2>
        <h2>Computed full name - {{fullName}}</h2>

        <button @click="changeFullName">Change full name</button>

        <h2>Total - {{items.reduce((total, curr) => total+curr.price,0)}}</h2>
        <h2>Computed Total - {{total}}</h2>
        <button @click="items.push({id: 4, title: 'mouse', price: 50})">Add Item</button>

        <!-- Difference between computed and method: computed properties are cached hnce improving app performance -->
        <h2>Method Total - {{getTotal()}}</h2>
        <input type="text" v-model="country">

        <template v-for="item in items" :key="item.id">
            <h2 v-if="item.price > 100">{{item.title}} {{item.price}}</h2>
        </template>

        <h2 v-for="item in expensiveItems" :key="item.id">{{item.title}} {{item.price}}</h2>

        <!-- Computed setters -->

    </div>
</template>

<script>
export default {
    name: "ComputedProperties",
    data() {
        return {
            firstName: 'Mayank',
            lastName: 'Mittal',
            items: [
                {
                    id: 1,
                    title: 'TV',
                    price: 100
                },
                {
                    id: 1,
                    title: 'Phone',
                    price: 200
                },
                {
                    id: 1,
                    title: 'Table',
                    price: 500
                }
            ],
            country: ''
        }
    },
    methods: {
        getTotal() {
            console.log("get total method")
            return this.items.reduce((total, curr) => total+curr.price,0)
        },
        changeFullName() {
            this.fullName = 'Mayank Mittall'
        }
    },
    computed: {
        fullName: {
            get() {
                return `${this.firstName} ${this.lastName}`
            },
            set(value) {
                const [first, last] = value.split(' ')
                this.firstName = first;
                this.lastName = last
            }
        },
        total() {
            console.log("total computed property")
            return this.items.reduce((total, curr) => total+curr.price,0)
        },
        expensiveItems() {
            return this.items.filter((item) => item.price > 100)
        }
    }
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