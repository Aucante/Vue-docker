<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld message="Composant HelloWorld" :users="users" />
    <HelloWorld message="Composant All Users" :users="users" />
    <button @click="fetchData">Fetch Data</button>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import axios from "axios";

export default {
  data() {
    return {
      nombre: Math.floor(Math.random() * 100 + 1),
      usersData: [],
    };
  },
  name: "App",
  components: {
    HelloWorld,
  },
  props: {
    message: String,
  },
  methods: {
    fetchData() {
      axios.get("https://randomuser.me/api/?results=10").then((response) => {
        console.log(response.data.results);
        this.usersData = response.data.results;
      });
    },
  },
  computed: {
    users() {
      return this.usersData; // Utilisation de la copie locale des données pour la prop 'users'
    },
  },
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
