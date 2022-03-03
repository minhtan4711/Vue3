<template>
  <h1>{{ title }}</h1>
  <input type="text" ref="input_name" />
  <button @click="handleClick">Click me</button>
  <div v-if="showModal">
    <modal :header="header" :text="text" @close="toggleModal" />
  </div>
  <button @click.shift="toggleModal">Open Modal (shift)</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      title: "My first vue app 2",
      header: "some random text",
      text: "another random text",
      showModal: false,
    };
  },
  methods: {
    handleClick() {
      console.log(this.$refs.input_name);
      this.$refs.input_name.classList.add("active");
      this.$refs.input_name.focus();
    },
    toggleModal() {
      this.showModal = !this.showModal;
    },
  },
};
</script>

<style >
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
