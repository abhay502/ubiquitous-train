<template>
    <div class="create-post-container">
      <h1>{{ title }}</h1>

      <div class="form-container">
        <form @submit.prevent="createPost">
          <div class="form-group">
            <label for="userId">Post userId</label>
            <input type="text" id="userId" v-model="formData.userId">
          </div>
  
          <div class="form-group">
            <label for="title">Post Title</label>
            <input type="text" id="title" v-model="formData.title">
          </div>
  
          <div class="form-group">
            <label for="body">Post Body</label>
            <input type="text" id="body" v-model="formData.body">
          </div>
  
          <div class="form-group">
            <button >Submit</button>
          </div>

        </form>
      </div>
    </div>
  </template>
  
  <script>
import axios from 'axios';
  export default {
    name: "CreatePost",
    data() {
      return {
        title: "Create a Post",
        formData: {
          userId: "",
          title: "",
          body: ""
        }
       
      };
    },
    methods:{
            createPost(){
                axios.post("https://jsonplaceholder.typicode.com/posts",this.formData)
                .then((res)=>{
                    console.log(res?.data)
                }).catch((err)=>{
                    console.log(err)
                })
            }
        }
  };
  </script>
  
  <style scoped>
  .create-post-container {
    max-width: 400px;
    margin: auto;
    padding: 20px;
    border: 1px solid #ddd;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  }
  
  .form-container {
    margin-top: 20px;
  }
  
  .form-group {
    margin-bottom: 15px;
  }
  
  label {
    display: block;
    margin-bottom: 5px;
    font-weight: bold;
  }
  
  input,
  textarea {
    width: 100%;
    padding: 8px;
    box-sizing: border-box;
    border: 1px solid #ddd;
    border-radius: 3px;
  }
  
  button {
    background-color: #4caf50;
    color: #fff;
    padding: 10px;
    border: none;
    border-radius: 3px;
    cursor: pointer;
  }
  </style>
  