<template>
  <div class="my-result">
    <div class="inner-div" :style="{opacity: visible ? 1 : 0}">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      visible: false
    };
  },
  created() {
    setInterval(() => {
      this.visible = !this.visible;
    }, 1000);
  }
};
</script>

<style>
.inner-div {
  transition: opacity 1s linear;
}
</style>
