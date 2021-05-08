<template>
  <h1>{{ title }}</h1>
  <div>
    <input type="text" ref="myInput" />
    <button @click="handleInput">click me</button>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      title: "This is my first vue app :)",
    };
  },
  methods: {
    handleInput() {
      this.$refs.myInput.focus();
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1 {
  display: inline-block;
  border-bottom: 1px solid #555;
  padding: 5px 10px;
}
</style>
