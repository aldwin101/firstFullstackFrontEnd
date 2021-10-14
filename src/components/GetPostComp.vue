<template>
    <div>
        <div id='post'>
            <p>{{username}}</p>
            <h3>{{content}}</h3>
        </div>
        <div>
            <button>Edit</button>
            <button>Delete</button>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'GetPostComp',
        props: {
                id: Number,
                content: String,
            } 
        }
</script>

<style scoped>

</style>