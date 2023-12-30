
  
  <script>
  export default {
    name: "PageViewer",
    data() {
      return {
        activePages: 0,
        pages: [
          {
            link: { text: "Home Page", url: "index.html" },
            pageTitle: "Home Page",
            content: "Welcome to the home page",
          },
          {
            link: { text: "About Page", url: "about.html" },
            pageTitle: "About Page", 
            content: "Welcome to the About page",
          },
          {
            link: { text: "Login Page", url: "login.html" },
            pageTitle: "Login Page",
            content: "Welcome to the Login page",
          },
        ],
      };
    },
  };
  </script>
  
  <template>
    <div>
      <h1>Page Viewer</h1>
      <div class="page-container">
        <div v-for="(page, index) in pages" :key="index" class="page">
          <h2>{{ page.pageTitle }}</h2>
          <p>{{ page.content }}</p>
          <router-link :to="page.link.url">{{ page.link.text }}</router-link>
        </div>
      </div>
    </div>
  </template>









  <style scoped>
  /* Add your styling here */
  .page-container {
    display: flex;
    justify-content: space-around;
    align-items: center;
  }
  
  .page {
    border: 1px solid #ccc;
    padding: 20px;
    margin: 10px;
    text-align: center;
  }
  
  h1 {
    text-align: center;
    color: #333;
  }
  
  /* Add more styles as needed */
  </style>
  