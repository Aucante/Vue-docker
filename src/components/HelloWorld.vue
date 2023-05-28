<template>
  <div class="hello">
    <h1>{{ message }}</h1>
    <button @click="fetchData">Fetch Data</button>
    <table>
      <tr v-for="user in users" :key="user.id">
        <td><img :src="user.picture.large" /></td>
        <td>
          {{ user.name.first }}
        </td>
      </tr>
    </table>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "HelloWorld",
  props: {
    message: String,
  },
  data() {
    return {
      users: [],
    };
  },
  methods: {
    fetchData() {
      axios.get("https://randomuser.me/api/?results=3").then((response) => {
        console.log(response.data.results);
        this.users = response.data.results;
      });
    },
  },
};
</script>

<style scoped>
/* Votre style personnalisé ici */
</style>
