<template>
  <h2>Peliculas</h2>

  <Form />
</template>

<script>
import Form from "./components/Form.vue";
export default {
  name: "App",
  components: {
    Form: Form,
  },
};
</script>

<style lang="scss">
@import "./styles/_variables.scss";
html,
body {
  background: $bg;
  color: $color;
  margin: o;
  font-family: sans-serif;
}
h2 {
  border-bottom: 1px solid $color;
  padding-bottom: 10px;
}
</style>
