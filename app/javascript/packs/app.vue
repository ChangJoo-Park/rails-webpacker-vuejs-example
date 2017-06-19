<template>
  <div id="app">
    <p>{{ message }}</p>
    <div class="">
      {{count}} <button @click="increase">+</button>
    </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      message: "Hello Vue!",
      count: 0
    }
  },
  methods: {
    increase () {
      this.count++
    }
  }
}
</script>

<style scoped>
p {
  font-size: 2em;
  text-align: center;
}
</style>
