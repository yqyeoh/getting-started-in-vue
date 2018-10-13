<template>
  <div class="counter">
    <div>Please pay ${{price}}</div>
    <button @click="increment">Click</button>
  </div>
</template>

<script>
export default {
  props: ['rate', 'available'],
  data () {
    return {
      count: 0
    }
  },
  computed: {
    price () {
      return this.rate * this.count
    }
  },
  methods: {
    increment () {
      if (this.available < this.rate) return
      this.count++
      this.$emit('update', this.rate)
    }
  }
}

</script>

<style lang="scss">
.counter {
  button {
    font-size: inherit;
  }
}
</style>
