<template>
   <user-card/>
</template>

<script>
import UserCard from './components/UserCard.vue'

    export default {
  components: { UserCard },
      name: 'App'
    }
</script>

<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    min-height:100vh;
    background-color: #F3F5FA;
  }
</style>
