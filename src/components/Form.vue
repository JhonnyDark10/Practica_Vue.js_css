<template>
  <form v-for="movie in movies">
    <h3>{{ movie.name }}</h3>

    <button
      type="button"
      v-on:click="movie.quantity -= 1"
      :disabled="movie.quantity <= 0"
    >
      -
    </button>
    {{ movie.quantity }}
    <button
      type="button"
      v-on:click="movie.quantity += 1"
      :disabled="movie.quantity >= movie.available"
    >
      +
    </button>
  </form>
</template>

<script>
export default {
  name: "Form",
  data() {
    return {
      movies: [
        {
          name: "avenger",
          available: 3,
          quantity: 0,
        },
        {
          name: "terminator",
          available: 5,
          quantity: 0,
        },
      ],
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import "../styles/_variables.scss";
form {
  background: $bg;
  border: 1px solid $color;
  margin: 0px 50px 25px;
  padding: 10px 25px 25px;
  text-align: center;
  transform: scale(1);
  transition: 0.3s transform;
}

form:hover {
  transform: scale(1.2);
}
button {
  background: $color2;
  border: 1px solid transparent;
  cursor: pointer;
  padding: 5px 10px;
  transition: border-color 0.15;
}
button:hover {
  border: 1px solid $color2;
}

button[disabled] {
  opacity: 0.5;
}
</style>
