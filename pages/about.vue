<template>
  <div class="container">
    <h1>About page</h1>
    <p>Check the source code to see the custom meta tags added with our custom component <code>twitter-head-card</code></p>
    <twitter-head-card />
    <nuxt-link to="/">Home page</nuxt-link>
    <p>It should take 5 seconds for the loader to disappear</p>
    <p>It should take 5 seconds for the route to change after you
    <span class="link" @click="goToFinal">click here</span></p>
  </div>
</template>

<script>
import TwitterHeadCard from '~/components/twitter-head-card.vue'

export default {
  loading: false,
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
  },
  mounted() {
    setTimeout(() => {
      this.$nuxt.$loading.finish()
    }, 5000)
  },
  methods: {
    goToFinal() {
      this.$nuxt.$loading.start()
      setTimeout(() => {
        this.$router.push('/final')
      }, 5000)
    }
  }
}
</script>

<style>
.link {
  cursor: pointer;
  text-decoration: underline;
}
.container {
  text-align: center;
  margin-top: 150px;
  font-size: 20px;
}
</style>