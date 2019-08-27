<template>
  <div id="app">
    <Header></Header>
    <Letters :letters="letters"></Letters>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Letters from "./components/Letters.vue";
import data from "./json/data.json";

export default {
  name: "app",
  components: {
    Header,
    Letters
  },
  data() {
    return {
      letters: data.abc
    };
  }
};
</script>

<style>
#app {
  font-family: "Montserrat", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  margin-bottom: 60px;
}

@media (max-width: 550px) {
  .block {
    grid-template-columns: 1fr;
  }
  #app {
    margin-top: 25px;
    margin-bottom: 25px;
  }
}
</style>
