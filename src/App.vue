<template>
  <div id="app">
    <my-component :label="labelA" @update="stateA=$event"></my-component>
    <div>x</div>
    <my-component :label="labelB" @update="stateB=$event"></my-component>
    <div>=</div>
    <my-result>{{result}}</my-result>
    <!-- <my-result></my-result> -->
  </div>
</template>

<script>
import MyComponent from "./components/MyComponent.vue";
import MyResult from "./components/MyResult.vue";

export default {
  name: "app",
  components: {
    MyComponent
  },
  data() {
    return {
      labelA: "A",
      labelB: "B",
      stateA: 0,
      stateB: 0
    };
  },
  computed: {
    result() {
      return this.stateA * this.stateB;
    }
  },
  methods: {
    log(msg) {
      console.log(msg);
    },
    updateAvailable(value) {
      this.available = this.available - value;
    },
    fetchItems() {
      setTimeout(() => {
        console.log("Items fetched");
        this.items = [
          { label: "Apple", price: 5 },
          { label: "Banana", price: 10 },
          { label: "Coconut", price: 20 }
        ];
      }, 1000);
    }
  },
  created() {
    this.fetchItems();
  }
};
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  font-size: 36px;

  display: flex;
  align-items: center;
  justify-content: center;
  & > div + div {
    margin-left: 30px;
  }
  .counter {
    margin-bottom: 1em;
  }
}
</style>
