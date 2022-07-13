<!-- creo il componente principale di vue -->
<template>
    <div>
        <div class="container">
            <h1 class=" text-center mb-3">Lista Post</h1>
            <ul>
                <li v-for="post in posts" :key="post.id">
                    <h3>{{ post.title }}</h3>
                    <p>{{ post.text }}</p>
                    <span class="text-light" v-for="tag in post.tags" :key="tag.id">
                        {{ tag.name }}
                    </span>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>



export default {
    data () {
        return {
            apiUrl:'http://127.0.0.1:8000/api/posts',
            posts: null
        }
    },
    methods:{
        getApi(){
            axios.get(this.apiUrl)
            .then(res =>{
                console.log(res.data);
                this.posts = res.data.posts;
            })
        }
    },
    mounted(){


        this.getApi();
    }
}
</script>

<style lang="scss" scoped>

</style>
