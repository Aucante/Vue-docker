<template>
  <div class="hello">
    <h1>{{ message }}</h1>
    <button @click="fetchData">Fetch Data</button>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "HelloWorld",
  props: {
    message: String,
  },
  methods: {
    fetchData() {
      axios.get("https://randomuser.me/api/?results=3").then((response) => {
        console.log(response.data);
      });
    },
  },
};
</script>

<style scoped>
/* Votre style personnalisé ici */
</style>
