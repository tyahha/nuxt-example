<template>
  <div class="container">
    <h1>Hello, {{ name }}!</h1>
    <p><nuxt-link to="/about" class="button is-medium is-primary hvr-float-shadow">I am a button</nuxt-link></p>
    <p><nuxt-link to="/about">About page</nuxt-link></p>
    <p><nuxt-link to="/users">User List</nuxt-link></p>
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