<template>
  <div id="app">
    <Header />
    <Main />
    <Footer />
  </div>
</template>

<script>
  import Header from './components/Header.vue'
  import Main from './components/Main.vue'
  import Footer from './components/Footer.vue'

  export default {
    name: 'App',
    components: {
      Header,
      Main,
      Footer
    }
  }
</script>

<style lang="scss">
  body {
    margin: 0px;
  }

  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;

    *,
    *::before,
    *::after {
      box-sizing: border-box;
    }

    h2 {
      margin-top: 2rem;
    }

    .bold {
      font-weight: bold;
    }

  }
</style>