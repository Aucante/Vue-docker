<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
img {
  float: left;
  margin-right: 1rem;
}
.misEnForme {
  background: #e0ffff;
  font-family: georgia;
  font-size: 1.2rem;
  margin: 1rem;
}
</style>
