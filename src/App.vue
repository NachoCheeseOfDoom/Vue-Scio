<template>
  <div class="context">
    <h1>Nothing to Show</h1>
    <h2>Choose an option</h2>

    <button v-on:click="showFoodsMethod">Favorit foods</button>
    <button v-on:click="showHelloWorld">Hello World</button>

    <div v-if="isHellowWorld">
      <img alt="Vue logo" src="./assets/logo.png" />
      <HelloWorld msg="Hellow World" />
      <HelloWorld class="message-test" myName="Soy Ignacio" />
      <HelloWorld age="23" />
      Lista de estudiantes
      <ul>
        <li v-for="(alumno, idx) in alumnos" :key="idx">
          {{ alumno }} Numero de letras en su nombre =
          {{ letterCounter(alumno) }}
        </li>
      </ul>
      <!-- ========================================== -->
      <!-- <ul>
      <li v-for="(meme, idx) in memes" :key="idx">
          {{ meme.meme }} 
        </li>
      </ul>

      <div>
        {{ memes }}
      </div> -->
    </div>

    <div v-else></div>

    <div v-if="showFoods">
      <HelloWorld msg="Soy Nacho" />
      <h2 class="favrit-food-title">Estas son mis comidas favoritas:</h2>
      <div>
        <ul>
          <li v-for="(comida, idx) in comidas" :key="idx">
            {{ showInUpperCase(comida) }}
          </li>
        </ul>

        <FavoritFoods
          style="color: dimgrey"
          :tacos="`Mis tacos favoritos son: ${showInUpperCase(tacos)}`" />
        <FavoritFoods
          style="color: dimgrey"
          :pizza="`De igual manera mis pizzas favoritas son: ${showInUpperCase(
            pizzas
          )}`" />
      </div>
    </div>
  </div>

  <div class="area">
    <ul class="circles">
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
    </ul>
  </div>

  <!-- <HelloWorld class="message-test" msg="Prueba" /> -->
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import FavoritFoods from "./components/FavoritFoods.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    HelloWorld,
    FavoritFoods,
  },
  data() {
    return {
      message: "Como estas mundo?",
      isHellowWorld: false,
      alumnos: ["Ignacio", "Diego", "Raul"],
      // companeros: [],
      // !!===================== Favorit foods ==============================
      // comida: {
      //   tacos: ["Asada", "Al pastor", "adobada"],
      //   tamales: [],
      //   pizza: ["Mexicana", "Peperoni", "Diabla", "pollo"],
      // },
      showFoods: false,
      comidas: ["Tacos", "tamales", "Pasta", "Pollo", "Hamburguesas", "Pizza"],
      tacos: " Asada, Al pastor y Adobada",
      pizzas: "Mexicana, Peperoni, Diabla, pollo",
    };
  },
  methods: {
    letterCounter(name) {
      return name.length;
    },
    showInUpperCase(word) {
      return word.toUpperCase();
    },
    showFoodsMethod() {
      return (this.showFoods = true) && (this.isHellowWorld = false);
      // console.log("hellos this is a test");
    },
    showHelloWorld() {
      return (this.isHellowWorld = true) && (this.showFoods = false);
      // console.log("hellos this is a test");
    },
  },
  // mounted() {
  //   axios
  //     .get("https://api.imageflip.com/get_memes")
  //     .then((response) => (this.memes = response.data.data.memes));
  // },
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
  /* background-color: rgba(199, 199, 199, 0.758); */
}
@import url("https://fonts.googleapis.com/css?family=Exo:400,700");
button {
  position: relative;
  z-index: 1;
  color: #4e54c8;
  background-color: white;
  padding: 10px 30px;
  margin-bottom: 5px;
  border: none;
  font-weight: bold;
  border-radius: 5px;
  cursor: pointer;
  transition: padding 0.15s, color 0.1s;
  margin-left: 10px;
}
button:hover {
  padding: 12px 32px;
  transition: padding 0.15s, color 0.1s;
}

button:active {
  background-color: #8b8fd1;
  color: white;
  padding: 10px 30px;
  /* opacity: .8; */
  transition: color 0.1s;
}
* {
  margin: 0px;
  padding: 0px;
}

body {
  font-family: "Exo", sans-serif;
}

.context {
  width: 100%;
  position: absolute;
  top: 50vh;
}

.context h1 {
  text-align: center;
  color: #fff;
  font-size: 50px;
}

.area {
  background: #4e54c8;
  background: -webkit-linear-gradient(to left, #8f94fb, #4e54c8);
  width: 100%;
  height: 100vh;
}

.circles {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.circles li {
  position: absolute;
  display: block;
  list-style: none;
  width: 20px;
  height: 20px;
  background: rgba(255, 255, 255, 0.2);
  animation: animate 25s linear infinite;
  bottom: -150px;
}

.circles li:nth-child(1) {
  left: 25%;
  width: 80px;
  height: 80px;
  animation-delay: 0s;
}

.circles li:nth-child(2) {
  left: 10%;
  width: 20px;
  height: 20px;
  animation-delay: 2s;
  animation-duration: 12s;
}

.circles li:nth-child(3) {
  left: 70%;
  width: 20px;
  height: 20px;
  animation-delay: 4s;
}

.circles li:nth-child(4) {
  left: 40%;
  width: 60px;
  height: 60px;
  animation-delay: 0s;
  animation-duration: 18s;
}

.circles li:nth-child(5) {
  left: 65%;
  width: 20px;
  height: 20px;
  animation-delay: 0s;
}

.circles li:nth-child(6) {
  left: 75%;
  width: 110px;
  height: 110px;
  animation-delay: 3s;
}

.circles li:nth-child(7) {
  left: 35%;
  width: 150px;
  height: 150px;
  animation-delay: 7s;
}

.circles li:nth-child(8) {
  left: 50%;
  width: 25px;
  height: 25px;
  animation-delay: 15s;
  animation-duration: 45s;
}

.circles li:nth-child(9) {
  left: 20%;
  width: 15px;
  height: 15px;
  animation-delay: 2s;
  animation-duration: 35s;
}

.circles li:nth-child(10) {
  left: 85%;
  width: 150px;
  height: 150px;
  animation-delay: 0s;
  animation-duration: 11s;
}

@keyframes animate {
  0% {
    transform: translateY(0) rotate(0deg);
    opacity: 1;
    border-radius: 0;
  }

  100% {
    transform: translateY(-1000px) rotate(720deg);
    opacity: 0;
    border-radius: 50%;
  }
}

.message-test {
  color: red;
}

.favrit-food-title {
  color: white;
}
.FavoritFoods {
  color: green;
}
</style>
