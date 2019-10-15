<template>
    <div class="container">
        <table class="table mt-4">
            <thead class="thead-dark">
                <tr>
                <th scope="col">User ID</th>
                <th scope="col">ID</th>
                <th scope="col">Title</th>
                <th scope="col">Body</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="post in posts" :key="post.id">
                <th scope="row">{{post.userId}}</th>
                <td>{{post.id}}</td>
                <td>{{post.title}}</td>
                <td>{{post.body}}</td>
                </tr>
            </tbody>
        </table>

            
    </div>
</template>
<script>
import axios from 'axios'
export default {
    name:'PostsExample',
    data(){
        return {
            posts: []
        }
    }, 
    created(){
        axios.get('https://jsonplaceholder.typicode.com/posts').then(posts => {
            this.posts = posts.data
        });
        console.log("It's working")
    }
}
</script>
<style>

</style>