<template>
  <h1>{{ title }}</h1>
  <input type="text" ref="input_name" />
  <button @click="handleClick">Click me</button>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      title: "My first vue app 2",
    };
  },
  methods: {
    handleClick() {
      console.log(this.$refs.input_name);
      this.$refs.input_name.classList.add("active");
      this.$refs.input_name.focus();
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
</style>
