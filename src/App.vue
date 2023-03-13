<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Soy Nacho" />
  <HelloWorld class="message-test" myName="Ignacio" />
  <HelloWorld age="24" />
  <!-- <HelloWorld class="message-test" msg="Prueba" /> -->
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: coral;
  margin-top: 60px;
  font-size: 30px;
}

.message-test {
  color: red;
}
</style>
