<template>
  <div class="container">
    <h1>About page</h1>
    <p>Check the source code to see the custom meta tags added with our custom component <code>twitter-head-card</code></p>
    <twitter-head-card />
    <nuxt-link to="/">Home page</nuxt-link>
  </div>
</template>

<script>
import TwitterHeadCard from '~/components/twitter-head-card.vue'

export default {
  asyncData() {
    return new Promise(resolve => {
      setTimeout(() => resolve({
        name: process.static ? 'static' : (process.server ? 'server' : 'client')
      }), 1000)
    })
  },
  head: {
    title: 'About page',
    meta: [
      { hid: 'description', name: 'description', content: 'About page description' }
    ]
  },
  components: {
    TwitterHeadCard
  }
}
</script>

<style>
.container {
  text-align: center;
  margin-top: 150px;
  font-size: 20px;
}
</style>