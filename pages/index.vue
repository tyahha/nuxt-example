<template>
  <div class="container">
    <h1>Hello, {{ name }}!</h1>
    <nuxt-link to="/about">About page</nuxt-link>
    <nuxt-link to="/users">User List</nuxt-link>
  </div>
</template>

<script>
export default {
  asyncData() {
    return new Promise(resolve => {
      setTimeout(() => resolve({ name: 'Vue World'}), 1000)
    })
  },
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