<!-- creo il componente principale di vue -->
<template>
    <div>
        <div class="container">
            <h1 class=" text-center mb-3">Lista Post</h1>
            <ul>
                <li v-for="post in posts" :key="post.id">
                    <h3>{{ post.title }}</h3>
                    <p>{{ post.text }}</p>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
import Axios from 'axios'



export default {
    data () {
        return {
            apiUrl:'http://127.0.0.1:8000/api/posts',
            posts: null
        }
    },
    methods:{
        getApi(){
            Axios.get(this.apiUrl)
            .then(res =>{
                this.posts = res.data.posts;
            })
        }
    },
    mounted(){
        console.log(axios);

        this.getApi();
    }
}
</script>

<style lang="scss" scoped>

</style>
