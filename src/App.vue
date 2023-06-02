<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld message="Composant HelloWorld" :users="users" />
    <HelloWorld message="Composant All Users" :users="users" />
    <button @click="compteur++">Click</button>
    {{ compteur }}
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  data() {
    return {
      compteur: 0,
    };
  },
  watch: {
    compteur(valeur) {
      if (valeur == 10) {
        this.compteur = 0;
      }
    },
  },
  name: "App",
  components: {
    HelloWorld,
  },
  props: {
    message: String,
  },
  methods: {},
  computed: {},
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
