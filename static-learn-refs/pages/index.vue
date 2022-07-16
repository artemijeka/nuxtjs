<template>
  <div>
    <Tutorial />
    <nav>
      <h2>Posts</h2>
      <nuxt-link
        v-for="post in posts"
        :to="{ name: 'posts-id', params: { id: post.id } }"
        :key="post.id"
        class="main-page-nav__item"
      >
        {{ post.title }}
      </nuxt-link>
    </nav>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  computed: {
    posts() {
      return this.$store.state.posts.all
    },
  },
}
</script>

<style lang="scss">
.main-page-nav {
  &__item {
    margin-right: 10px;
  }
}
</style>
