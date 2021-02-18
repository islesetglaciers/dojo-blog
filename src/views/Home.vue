<template>
  <div class="home">
    <h1>Home</h1>
    <PostList :posts="posts" />
  </div>
</template>

<script>
// @ is an alias to /src
import PostList from '../components/PostList'
import { ref } from 'vue'

export default {
  name: 'Home',
  components: { PostList },
  setup() {
    const posts = ref([
      { title: 'Welcome to the blog', id: 1, body: 'Lorem ipsum dolor sit amet' },
      { title: 'Top 5 CSS Tips', id: 2, body: 'Lorem ipsume dolor sit amet' }
    ])

    return { posts }
  }
}
</script>
