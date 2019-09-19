<template>
  <div id="app">
    <Header></Header>
    <Letters class="lettersMain" :letters="letters"></Letters>
    <p class="footer">Made with ❤️ by Paz and Nelson</p>
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
body {
  padding: 0;
  margin: 0;
}
#app {
  font-family: "Montserrat", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  margin-bottom: 60px;
}

.lettersMain {
  margin: 0 15vw;
}

.footer {
  margin: 60px;
}

@media (max-width: 550px) {
  #app {
    margin-top: 25px;
    margin-bottom: 25px;
  }
  .lettersMain {
    margin: 0 5vw;
  }
}
</style>
