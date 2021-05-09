<template>
  <h1 id="app-title">{{ title }}</h1>
  <div>
    <button @click="handleInput">Show Modal</button>
  </div>
  <p>hello from app</p>
  <modal @getModalRef="saveModalRef" />
</template>

<script>
import Modal from "./components/Modal";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "This is my first vue app :)",
      modalRef: "",
    };
  },
  methods: {
    handleInput() {
      this.modalRef.style.display = "block";
    },
    saveModalRef(value) {
      this.modalRef = value;
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

h1#app-id {
  display: inline-block;
  border-bottom: 1px solid #555;
  padding: 5px 10px;
}
</style>
