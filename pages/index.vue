<template>
  <div class="container">
    <h1>Welcome!</h1>
    <nuxt-link to="/about">About page</nuxt-link>
  </div>
</template>

<script>
export default {
  head: {
    title: 'Home page',
    meta: [
      { hid: 'description', name: 'description', content: 'Home page description' }
    ],
    noscript: [
      { innerHTML: 'Body No Scripts', body: true }
    ],
    script: [
      { src: '/head.js' },
      { src: '/body.js', body: true },
      { src: '/defer.js', defer: '' }
    ]
  },
}
</script>

<style>
.container {
  text-align: center;
  margin-top: 150px;
  font-size: 20px;
}
</style>