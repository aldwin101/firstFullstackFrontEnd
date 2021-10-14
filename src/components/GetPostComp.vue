<template>
    <div>
        <div id='post'>
            <p>{{username}}</p>
            <h3>{{content}}</h3>
        </div>
        <div>
            <button @click="editPost">Edit</button>
            <button @click="deletePost">Delete</button>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
    export default {
        name: 'GetPostComp',
        props: {
            postId: Number,
            postContent: String,
        },
        data() {
        return {
            id: this.postId,
            content: this.postContent,
            }
        },
        methods: {
            editPost() {
                axios.request({
                    url : 'https://firstfullstack.ga/api/posts',
                    method : 'PATCH',
                    headers : {
                        'Content-Type': 'application/json',
                    },
                    data: {
                        'content': this.content
                    }
                }).then((response) => {
                    this.posts = response.data;
                }).catch((error) => {
                    console.log(error);
                })
            },

            deletePost() {
                axios.request({
                    url : 'https://firstfullstack.ga/api/posts',
                    method : 'PATCH',
                    headers : {
                        'Content-Type': 'application/json',
                    },
                    data: {
                        'id': this.id
                    }
                }).then((response) => {
                    this.posts = response.data;
                }).catch((error) => {
                    console.log(error);
                })
            }
        },
    }
</script>

<style scoped>

</style>