<template>
  <div id="app">
    <my-counter ref="counter" v-for="item in items"
      :key="item.label"
      :rate="item.price"
      :available="available"
      @update="updateAvailable">
    </my-counter>
  </div>
</template>

<script>
import MyCounter from './components/MyCounter.vue'

export default {
  name: 'app',
  components: {
    MyCounter
  },
  data () {
    return {
      available: 100,
      items: []
    }
  },
  methods: {
    log (msg) {
      console.log(msg)
    },
    updateAvailable (value) {
      this.available = this.available - value
    },
    fetchItems () {
      setTimeout(() => {
        console.log('Items fetched')
        this.items = [
          { label: 'Apple', price: 5 },
          { label: 'Banana', price: 10 },
          { label: 'Coconut', price: 20 }
        ]
      }, 1000)
    }
  },
  created () {
    this.fetchItems()
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
  font-size: 36px;

  .counter {
    margin-bottom: 1em;
  }
}
</style>
