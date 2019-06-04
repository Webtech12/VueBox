<template>
  <div class="blogs">
    <h2>{{ blogTitle }}</h2>
    <div v-for="post in posts" :key="post.id">
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
    posts: []
    }
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
