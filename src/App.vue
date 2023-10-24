<template>
  <div id="app">
    <h1>Picture Gallery</h1>
    <TheGallery />
  </div>
</template>

<script>
import TheGallery from './components/TheGallery.vue';

export default {
  name: 'App',
  components: {
    TheGallery: TheGallery,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1 {
  color: #fff;
}

body {
  border-color: #69655d;
  color: #ece1ca;
  background-color: #676769;
}
</style>
