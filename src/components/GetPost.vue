<template>
    <div>
        <GetPostComp v-for='post in posts' :key='post.id' 
        :postId='post.id'
        :postContent='post.content' />
    </div>
</template>

<script>
import axios from 'axios'
import GetPostComp from './GetPostComp.vue'
    export default {
        name: 'GetPost',
        components: {
            GetPostComp,
        },
        data() {
            return {
                posts: [],
            }
        },
        mounted () {
            axios.request({
                url: 'https://firstfullstack.ga/api/posts',
                method: 'GET',
                headers: {
                        'Content-Type': 'application/json',
                    },
                    params: {
                        id: this.id,
                    }  
                }).then((response) => {
                    this.posts = response.data;
                }).catch((error) => {
                    console.log(error);
                })
            }
        }
</script>

<style scoped>

</style>