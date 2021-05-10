<template>
  <h1 id="app-title">{{ title }}</h1>
  <div>
    <button @click="toggleModalOne" style="margin-right: 5px">
      Show Modal One
    </button>
    <button @click.alt="toggleModalTwo">Show Modal Two (Alt)</button>
  </div>
  <p>hello from app</p>
  <teleport to="#modals" v-if="showModalOne">
    <modal @close="toggleModalOne" title="Modal Title" theme="sale">
      <div>Slot!</div>
      <template v-slot:content> custom content </template>
    </modal>
  </teleport>

  <teleport to="#modals" v-if="showModalTwo">
    <modal @close="toggleModalTwo" title="Modal Two Title" theme="">
      <div>Another Slot!</div>
      <template v-slot:content> another custom content </template>
    </modal>
  </teleport>
</template>

<script>
import Modal from "./components/Modal";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "This is my first vue app :)",
      showModalOne: false,
      showModalTwo: false,
    };
  },
  methods: {
    toggleModalOne() {
      this.showModalOne = !this.showModalOne;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    },
  },
};
</script>

<style>
#app,
#modals {
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
