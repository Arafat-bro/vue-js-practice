<template>
    <div>
        <!-- <button @click="getPosts">Load Posts</button> -->
        <h3 v-if="errMsg">{{errMsg}}</h3>
        <div v-for="post in posts" :key="post.id">{{post.id}} - {{post.title}}</div>
    </div>
</template>

<script>
import axios from 'axios'
    export default {
        name: 'LoadPosts',
        created() {
            this.getPosts()   //get on reload
        },
        data() {
            return {
                posts: [],
                errMsg : '',
            }
        },
        methods: {
            getPosts(){
                axios
                .get('https://jsonplaceholder.typicode.com/posts')
                .then((response) => {
                    this.posts = response.data
                    //console.log(response.data)
                })
                .catch((error) =>{
                    //console.log(error)
                    this.errMsg = error
                })
            }
        },
    }
</script>

<style scoped>

</style>