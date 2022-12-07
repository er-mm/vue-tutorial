<template>
    <div>
        <button @click="getPosts">Load Posts</button>
        <h3 v-if="errMsg">{{errMsg}}</h3>
        <div v-for="post in posts" :key="post.id">
            <h3>{{post.id}}, {{post.title}}</h3>
            <p>{{post.body}}</p>
            <hr />
        </div>
    </div>
</template>

<script>
import axios from 'axios'
    export default {
        name: 'PostList',
        created() {
            this.getPosts()
        },
        data() {
            return {
                posts: [],
                errMsg: ''
            }
        },
        methods: {
            getPosts() {
                axios.get('https://jsonplaceholder.typicode.com/posts')
                .then((res) => {
                    console.log(res.data);
                    this.posts = res.data;
                })
                .catch(err => { 
                    console.log(err)
                    this.errMsg = "retriving data"
            })
            }
        }
    }
</script>

<style scoped>

</style>