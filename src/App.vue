<template>
  <div id="app">
    <Users></Users>
    <Todos></Todos>
    <Photos></Photos>
    <Comments></Comments>
    <Posts></Posts>
  </div>
</template>

<script>
import Users from './components/Users.vue'
import Todos from './components/Todos.vue'
import Photos from './components/Photos.vue'
import Comments from './components/Comments.vue'
import Posts from './components/Posts.vue'

export default {
  name: 'App',
  components: {
    Users,
    Todos,
    Photos,
    Comments,
    Posts
  }
}
</script>

<style>
/*#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

li {
  list-style-type: none;
}*/
</style>
