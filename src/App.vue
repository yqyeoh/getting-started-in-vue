<template>
  <div id="app">
    <img src="./assets/logo.png" />
    <hello-world :msg="message"></hello-world>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    HelloWorld
  },
  data () {
    return {
      message: 'getting-started-in-vue'
    }
  },
  methods: {
    log (msg) {
      console.log(msg)
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  font-size: 16px;

  .counter {
    margin-bottom: 1em;
  }
}
</style>
