<template>
  <b-container>
    <post-card
      v-for="post in posts"
      :key="post.id"
      :id="post.id"
      :date="post.date"
      :title="post.title"
      :description="post.description"
      :pictures="post.pictures"  
    />
  </b-container>
</template>

<script>
import Posts from '../data/posts.json'
import PostCard from '../components/PostCard.vue'

export default {
  components: {
    PostCard,
  },
  data() {
    return {
      posts: Posts
    }
  }
};
</script>
