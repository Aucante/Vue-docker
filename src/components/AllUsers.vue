<template>
  <div class="hello">
    <h1>{{ message }}</h1>
    <ul>
      <li v-for="user in users" :key="user.email">
        {{ user.name.first }} {{ user.name.last }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    message: String,
    users: Array,
  },
};
</script>

<style scoped>
/* Votre style personnalisé ici */
</style>
