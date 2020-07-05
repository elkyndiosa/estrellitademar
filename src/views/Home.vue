<template>
  <div class="home">
    <Search></Search>
    <v-col cols="12" v-for="(item, index) in posts" :key="index">
      <v-card :color="item.color" dark>
        <v-card-title class="headline" v-text="item.title"></v-card-title>
        <v-card-subtitle  v-text="item.body"></v-card-subtitle>
        <v-card-actions>
          <v-btn text>Listen Now</v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </div>
</template>
<script>
// @ is an alias to /src
import Search from "@/components/Search.vue";
import axios from "axios";
export default {
  name: "Home",
  components: {
    Search
  },
  data() {
    return {
      posts: [],
      colors: [
        '#5C257F',
        '#D697FF',
        '#B84BFF',
        '#6B4C7F',
        '#933CCC'
      ]
    };
  },
  created() {
    this.getPost();
  },
  methods: {
    getPost() {
      let url = "https://jsonplaceholder.typicode.com/posts";
      axios.get(url).then(response => {
        this.posts = response.data;
        this.posts.forEach(post => {
          post.color = this.colors[Math.floor(Math.random() * (5 - 0) + 0)]
        })
        console.log(this.posts);
      });
    }
  }
  
};
</script>
