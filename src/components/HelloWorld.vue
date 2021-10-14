<template>
    <div id="container">
        <div id="postContainer">
            <textarea v-model="content"></textarea>
            <button @click="postSomething">Post</button>
        </div>
    </div>
</template>

<script>
    import axios from 'axios'
    export default {
        name : 'HelloWorld',
        data(){
            return {
                content:'',
            }
        },
        methods: {
            postSomething(){
                axios.request({
                    url : 'https://firstfullstack.ga/api/posts',
                    method : 'POST',
                    headers : {
                        'Content-Type': 'application/json'
                    },
                    data: {
                        'content': this.content
                    }
                }).then((response) => {
                    console.log(response.data);
                }).catch((error) => {
                    console.log(error.response);
                })
            }
        }
    }
</script>

<style scoped>

#container {
    display: grid;
    grid-template-rows: 1fr 1fr;
}

#postContainer {
    display: grid;
    grid-template-rows: 1fr 1fr;
    width: 50vw;
}

button {
    width: 20vw;
}

</style>