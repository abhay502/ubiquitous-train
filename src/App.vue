<template>
  
  <div>
    <!-- <h1>{{name}} and he is a {{ domain }}</h1>
    <h2 v-text="location"></h2> -->
    <PostsList />
    <!-- <CreatePost /> -->
  </div>

</template>
 


<script>
import PostsList from './components/Posts.vue';
// import CreatePost from './components/CreatePost.vue';
export default {
  name: 'App',
  components:{
    PostsList,
    // CreatePost
  },
  data(){
    return{
      name:"Abhay S Nath",
      domain:"Mern stack developer",
      location:"from chennai"
      
    }
  }
  
}
</script>
  


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
