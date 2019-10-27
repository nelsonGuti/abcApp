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

body::after {
  content: "";
  background-color: #cbd6cc;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='200' height='200' viewBox='0 0 200 200'%3E%3Cg %3E%3Cpolygon fill='%23798f7e' points='100 57.1 64 93.1 71.5 100.6 100 72.1'/%3E%3Cpolygon fill='%2393ad99' points='100 57.1 100 72.1 128.6 100.6 136.1 93.1'/%3E%3Cpolygon fill='%23798f7e' points='100 163.2 100 178.2 170.7 107.5 170.8 92.4'/%3E%3Cpolygon fill='%2393ad99' points='100 163.2 29.2 92.5 29.2 107.5 100 178.2'/%3E%3Cpath fill='%23adccb4' d='M100 21.8L29.2 92.5l70.7 70.7l70.7-70.7L100 21.8z M100 127.9L64.6 92.5L100 57.1l35.4 35.4L100 127.9z'/%3E%3Cpolygon fill='%23748f67' points='0 157.1 0 172.1 28.6 200.6 36.1 193.1'/%3E%3Cpolygon fill='%238dad7d' points='70.7 200 70.8 192.4 63.2 200'/%3E%3Cpolygon fill='%23a6cc93' points='27.8 200 63.2 200 70.7 192.5 0 121.8 0 157.2 35.3 192.5'/%3E%3Cpolygon fill='%238dad7d' points='200 157.1 164 193.1 171.5 200.6 200 172.1'/%3E%3Cpolygon fill='%23748f67' points='136.7 200 129.2 192.5 129.2 200'/%3E%3Cpolygon fill='%23a6cc93' points='172.1 200 164.6 192.5 200 157.1 200 157.2 200 121.8 200 121.8 129.2 192.5 136.7 200'/%3E%3Cpolygon fill='%23748f67' points='129.2 0 129.2 7.5 200 78.2 200 63.2 136.7 0'/%3E%3Cpolygon fill='%23a6cc93' points='200 27.8 200 27.9 172.1 0 136.7 0 200 63.2 200 63.2'/%3E%3Cpolygon fill='%238dad7d' points='63.2 0 0 63.2 0 78.2 70.7 7.5 70.7 0'/%3E%3Cpolygon fill='%23a6cc93' points='0 63.2 63.2 0 27.8 0 0 27.8'/%3E%3C/g%3E%3C/svg%3E");
  opacity: 0.1;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  position: absolute;
  z-index: -1;
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
