<template>
    <div class="posts-container">
      <div class="posts-wrapper">
        <!-- <button @click="getPosts">Show Posts</button> -->
        <div v-for="post in posts" :key="post.id" class="post-card">
          <h3 class="post-title">{{ post?.title }}</h3>
          <p class="post-body">{{ post?.body }}</p>
        </div>
      </div>
    </div>
  </template> 
  
  <script>
  import axios from 'axios';
  
  export default {
    name: "PostsList",
    data() {
      return {
        posts: [],
      };
    },
    created() {
      this.getPosts();
    },
    methods: {
      getPosts() {
        axios
          .get("https://jsonplaceholder.typicode.com/posts")
          .then((res) => {
            this.posts = res?.data;
          })
          .catch((err) => {
            console.log(err);
          });
      },
    },
  };
  </script>
  
  <style>
  .posts-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
   
  }
  
  .posts-wrapper {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 20px;
  }
  
  .post-card {
    background-color: #cccaca;
    border: 2px solid blueviolet;
    border-radius: 8px;
    padding: 20px;
    transition: transform 0.3s ease-in-out;
  }
  
  .post-card:hover {
    transform: scale(1.05);
  }
  
  .post-title {
    color: rgb(61, 43, 226);
    font-size: 1.5rem;
    margin-bottom: 10px;
  }
  
  .post-body {
    font-size: 1rem;
    color: #000000;
  }
  </style>
  