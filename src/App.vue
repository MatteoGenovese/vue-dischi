<template>
  <div id="app">
      <Header />
      <Main />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'


export default {
  name: 'App',
  components: {
    Header,
    Main
}
}
</script>

<style lang="scss">
 @import "~bootstrap/scss/bootstrap.scss";
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
