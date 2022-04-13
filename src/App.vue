<template>
  <div id="app">
    <contenu />
    <header-top />
  </div>
</template>

<script>

import Content from './components/Content.vue';
import Header from './components/Header.vue';

export default {
  name: 'App',
  components: {
    'contenu': Content,
    'header-top': Header
  }
}
</script>

<style>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
} */
</style>
