<template>
  <div id="app">
    <!-- header  -->
    <Header />

    <!-- main  -->
    <Main />

    <!-- footer  -->

  </div>
</template>

<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';

export default {
  name: 'App',
  components: {
    Main,
    Header
  }
}
</script>

<style lang="scss">
// general rules
@import '~bootstrap/scss/bootstrap.scss';
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
</style>
