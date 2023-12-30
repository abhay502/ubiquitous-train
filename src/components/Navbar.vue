
  <script>
  export default { 
    name: "MyNavbar",
    data() {
      return {
        navItems: ["Home Page", "Login Page", "About Page"],
      };
    },
    methods: {
      getLink(item) {
        // You can customize the URL structure based on your needs
        return item.toLowerCase().replace(/\s/g, "-") + ".html";
      },
    },
  };
  </script>



<template>
    <nav>
      <ul>
        <li v-for="(item, index) in navItems" :key="index">
          <router-link :to="getLink(item)">{{ item }}</router-link>
        </li>
      </ul>
    </nav>
  </template>
  

















  
  <style scoped>
  nav {
    background-color: #333;
    padding: 10px;
  }
  
  ul {
    list-style-type: none;
    display: flex;
    justify-content: space-around;
    padding: 0;
  }
  
  li {
    margin: 0;
  }
  
  router-link {
    text-decoration: none;
    color: white;
    font-weight: bold;
  }
  
  /* Add more styles as needed */
  </style>
  