<template>
  <div>
    <HelloWorld />
    <GetPost />
  </div>
</template>

<script>
import GetPost from './components/GetPost.vue'
import HelloWorld from './components/HelloWorld.vue'
  export default {
    name: 'App',
    components : {
      HelloWorld,
      GetPost
    }
  }
</script>

<style scoped>

</style>