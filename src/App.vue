<template>
  <div id="app">
    <Navigation :navIcons="navIcons" @selectionState="setState"></Navigation>
    <Header></Header>
    <!-- parent : {{selectedState}} -->
    <Letters v-if="selectedState === 'letters'" class="cardsMain" :letters="letters"></Letters>
    <Numbers v-if="selectedState === 'numbers'" class="cardsMain" :numbers="numbers"></Numbers>
    <CardContainer v-if="selectedState === 'shapes'" class="cardsMain" :shapes="shapes"></CardContainer>
    <p class="footer">Made with ❤️ by Paz and Nelson</p>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Letters from "./components/Letters.vue";
import CardContainer from "./components/CardContainer.vue";
import Numbers from "./components/Numbers.vue";
import Navigation from "./components/Navigation.vue";
import data from "./json/data.json";
import { faFont, faListOl, faShapes } from "@fortawesome/free-solid-svg-icons";

export default {
  name: "app",
  components: {
    Header,
    Letters,
    CardContainer,
    Numbers,
    Navigation
  },
  data() {
    return {
      letters: data.abc,
      numbers: data.numbers,
      shapes: data.shapes,
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
  background-color: #f3f6f3;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='152' height='152' viewBox='0 0 152 152'%3E%3Cg fill-rule='evenodd'%3E%3Cg id='temple' fill='%23d5eeb0' fill-opacity='0.3'%3E%3Cpath d='M152 150v2H0v-2h28v-8H8v-20H0v-2h8V80h42v20h20v42H30v8h90v-8H80v-42h20V80h42v40h8V30h-8v40h-42V50H80V8h40V0h2v8h20v20h8V0h2v150zm-2 0v-28h-8v20h-20v8h28zM82 30v18h18V30H82zm20 18h20v20h18V30h-20V10H82v18h20v20zm0 2v18h18V50h-18zm20-22h18V10h-18v18zm-54 92v-18H50v18h18zm-20-18H28V82H10v38h20v20h38v-18H48v-20zm0-2V82H30v18h18zm-20 22H10v18h18v-18zm54 0v18h38v-20h20V82h-18v20h-20v20H82zm18-20H82v18h18v-18zm2-2h18V82h-18v18zm20 40v-18h18v18h-18zM30 0h-2v8H8v20H0v2h8v40h42V50h20V8H30V0zm20 48h18V30H50v18zm18-20H48v20H28v20H10V30h20V10h38v18zM30 50h18v18H30V50zm-2-40H10v18h18V10z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
}

#app {
  font-family: "Montserrat", sans-serif;
  font-size: 0.9rem;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  /* margin-bottom: 60px; */
}

.cardsMain {
  margin: 0 15vw;
}

.footer {
  margin-top: 60px;
  margin-bottom: 0;
  padding-bottom: 60px;
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
