<template>
  <div id="app">
    <Skills />
  </div>
</template>

<script>
import Skills from "./components/Skills.vue";

export default {
  name: "app",
  components: {
    Skills
  }
};
</script>

<style>
html,
body {
  margin: 0;
  height: 100vh;
}
body {
  background: #eeeeee;
  font-family: "Nunito", sans-serif;
  display: grid;
  grid-template-rows: auto;
  justify-content: center;
  padding-top: 3rem;
}

#app {
  width: 50vw;
}
</style>

