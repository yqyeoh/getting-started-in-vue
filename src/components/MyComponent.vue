<template>
  <div class="my-component">
    <div>{{label}}</div>
    <div>{{count}}</div>
    <button @click="increment">+ {{label}}</button>
  </div>
</template>

<script>
export default {
  props: ["label"],
  data() {
    return {
      count: 0
    };
  },
  methods: {
    increment() {
      this.count++;
      this.$emit("update", this.count);
    }
  }
};
</script>

<style>
</style>
