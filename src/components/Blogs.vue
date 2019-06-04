<template>
  <div class="blogs">
    <h2>{{ blogTitle }}</h2>
    <input type="text" v-model="searchTerm">
    <div v-for="post in filteredPosts" :key="post.id">
    <h3>{{ post.title }}</h3>
    <p>{{ post.body }}</p>
    <hr>
    </div>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'Blogs',
  data () {
    return {
    blogTitle: 'Blog Title',
    posts: [],
    searchTerm: ''
    }
  },
computed: {
  filteredPosts() {
    return this.posts.filter(post => {
      return post.title.match(this.searchTerm)
    })
  },
},

  methods: {
  
  },
 
  created() {
    axios.get('https://jsonplaceholder.typicode.com/posts')
    .then((res) => {
      this.posts = res.data
    }).catch((err) => {
      console.log(err);
    });
  },

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
