<template>
  <div class="home">
    <h1>Home</h1>
    <div v-if="error">{{ error }}</div>
    <div v-if="posts.length">
      <PostList :posts="posts" v-if="showPosts" />
    </div>
    <div v-else>Loading...</div>
    <!-- <button @click="showPosts = !showPosts">Toggle posts</button> -->
    <!-- <button @click="posts.pop()">Delete a post</button> -->
  </div>
</template>

<script>
// @ is an alias to /src
import PostList from '../components/PostList'
import getPosts from '../composables/getPosts'
import { ref } from 'vue'

export default {
  name: 'Home',
  components: { PostList },
  setup() {
    const showPosts = ref(true)

    const { posts, error, load } = getPosts()

    load()

    return { posts, showPosts, error }
  }
}
</script>
