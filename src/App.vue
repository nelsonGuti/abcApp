<template>
  <div id="app">
    <Navigation :navIcons="navIcons" @selectionState="setState"></Navigation>
    <Header></Header>
    <!-- parent : {{selectedState}} -->
    <Letters v-if="selectedState === 'letters'" class="cardsMain" :letters="letters"></Letters>
    <Numbers v-if="selectedState === 'numbers'" class="cardsMain" :numbers="numbers"></Numbers>
    <p class="footer">Made with ❤️ by Paz and Nelson</p>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Letters from "./components/Letters.vue";
import Numbers from "./components/Numbers.vue";
import Navigation from "./components/Navigation.vue";
import data from "./json/data.json";
// import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import { faFont, faListOl, faShapes } from "@fortawesome/free-solid-svg-icons";

export default {
  name: "app",
  components: {
    Header,
    Letters,
    Numbers,
    Navigation
  },
  data() {
    return {
      letters: data.abc,
      numbers: data.numbers,
      navIcons: [
        [faFont, "letters"],
        [faListOl, "numbers"],
        [faShapes, "shapes"]
      ],
      selectedState: "letters"
    };
  },
  computed: {
    appIcon() {
      return "";
    }
  },
  methods: {
    setState(state) {
      // console.log("event is captured in parent", state);
      this.selectedState = state;
    }
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
  font-size: 0.9rem;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  margin-bottom: 60px;
}

.cardsMain {
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
  .cardsMain {
    margin: 0;
  }
}
</style>
