<!-- creo il componente principale di vue -->
<template>
    <div>
        <div class="container">
            <h1>Lista Post</h1>
            <ul>
                <li v-for="item in items" :key="item.id">
                    {{ item }}
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
            apiUrl:'http://127.0.0.1:8000/api/posts'
        }
    },
    methods:{
        getApi(){
            Axios.get(this.apiUrl)
            .then(res =>{
                console.log(res.data)
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
