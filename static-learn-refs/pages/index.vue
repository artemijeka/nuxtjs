<template>
  <div>
    <Tutorial />
    <nav>
      <h2>Posts</h2>
      <nuxt-link
        v-for="post in posts"
        :key="post.id"
        :to="{ name: 'posts-id', params: { id: post.id } }"
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
  head() {
    return {
      title: 'Nuxt + Vue + Vuex | Home page!',
      meta: [
        { name: 'twitter:title', content: 'Nuxt + Vue + Vuex | Home page!' },
        { name: 'twitter:description', content: 'Home page! Nuxt + Vue + Vuex = Power&Speed' },
        { name: 'twitter:image', content: 'https://i.ytimg.com/vi/yHrSHiBSP4U/maxresdefault.jpg' },
        { name: 'twitter:card', content: 'summary_large_image' },
      ],
    }
  },
  computed: {
    posts() {
      return this.$store.state.posts.all
    },
  }
}
</script>

<style lang="scss">
.main-page-nav {
  &__item {
    margin-right: 10px;
  }
}
</style>
