<template>
  <div>
    <div class="letter-grid">
      <div class="item" :class="{ toggleCase: toggleCase }" @click="toggleCase = !toggleCase">
        <h1>{{letter.name}}</h1>
      </div>

      <div v-if="imageLoaded" class="item image">
        <div class="placeholder"></div>
        <transition appear name="slide-fade">
          <img class="imageLoaded" :src="imageLoaded" alt ref="image1" />
        </transition>
      </div>

      <div class="item loading" v-else-if="loading || !imageLoaded">
        <div class="loader">Loading...</div>
      </div>
      <div class="item" v-else-if="errored">Could not find the picture</div>

      <div class="item">
        <p
          v-for="(word,index) in letter.words"
          :key="index"
          :class="{selectedWord: word === selectedWord}"
        >{{word}}</p>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Letter",
  props: {
    letter: {
      type: Object
    }
  },
  data: function() {
    return {
      image: null,
      loading: true,
      errored: false,
      toggleCase: false,
      selectedWord: null
    };
  },
  computed: {
    imageLoaded: function() {
      return this.image;
    }
  },
  mounted() {
    axios
      .get(this.getRandomImageURL(this.letter.words))
      .then(response => {
        this.image = response.config.url;
      })
      .catch(error => {
        console.log(error);
        this.errored = true;
      })
      .finally(() => (this.loading = false));
  },
  methods: {
    getRandomImageURL: function(arr) {
      const randomIndex = Math.floor(Math.random() * Math.floor(3));
      const selectedWord = arr[randomIndex];
      this.selectedWord = selectedWord;
      return `https://source.unsplash.com/125x125/?${arr[randomIndex]}`;
    }
  }
};
</script>

<style scoped>
.slide-fade-enter-active {
  transition: all 1.5s ease;
}
.slide-fade-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}
.slide-fade-enter,
.slide-fade-leave-to {
  transform: translateX(20px);
  opacity: 0;
}

h1 {
  font-size: 4rem;
}

.toggleCase {
  color: rgb(185, 28, 125);
  text-transform: uppercase;
}
.letter-grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  height: 35vh;
  box-shadow: 0 14px 28px rgba(0, 0, 0, 0.25), 0 10px 10px rgba(0, 0, 0, 0.22);
  row-gap: 25px;
  border-radius: 5%;
}
.item {
  display: grid;
  justify-content: center;
  align-content: center;
}

.item.loading {
  min-width: 125px;
}

.imageLoaded {
  border-radius: 50%;
  grid-area: 1 / 1;
  width: 100%;
}
img {
  width: 100% !important;
}

.placeholder {
  background-color: white;
  width: 125px;
  height: 125px;
  border-radius: 50%;
  grid-area: 1 / 1;
}

.selectedWord {
  background-color: rgb(207, 224, 219);
  border-radius: 10%;
  padding: 0.35rem;
}

.loader {
  color: #2c3e50;
  font-size: 50px;
  text-indent: -9999em;
  overflow: hidden;
  width: 1em;
  height: 1em;
  border-radius: 50%;
  margin: 72px auto;
  position: relative;
  -webkit-transform: translateZ(0);
  -ms-transform: translateZ(0);
  transform: translateZ(0);
  -webkit-animation: load6 1.7s infinite ease, round 1.7s infinite ease;
  animation: load6 1.7s infinite ease, round 1.7s infinite ease;
}
@-webkit-keyframes load6 {
  0% {
    box-shadow: 0 -0.83em 0 -0.4em, 0 -0.83em 0 -0.42em, 0 -0.83em 0 -0.44em,
      0 -0.83em 0 -0.46em, 0 -0.83em 0 -0.477em;
  }
  5%,
  95% {
    box-shadow: 0 -0.83em 0 -0.4em, 0 -0.83em 0 -0.42em, 0 -0.83em 0 -0.44em,
      0 -0.83em 0 -0.46em, 0 -0.83em 0 -0.477em;
  }
  10%,
  59% {
    box-shadow: 0 -0.83em 0 -0.4em, -0.087em -0.825em 0 -0.42em,
      -0.173em -0.812em 0 -0.44em, -0.256em -0.789em 0 -0.46em,
      -0.297em -0.775em 0 -0.477em;
  }
  20% {
    box-shadow: 0 -0.83em 0 -0.4em, -0.338em -0.758em 0 -0.42em,
      -0.555em -0.617em 0 -0.44em, -0.671em -0.488em 0 -0.46em,
      -0.749em -0.34em 0 -0.477em;
  }
  38% {
    box-shadow: 0 -0.83em 0 -0.4em, -0.377em -0.74em 0 -0.42em,
      -0.645em -0.522em 0 -0.44em, -0.775em -0.297em 0 -0.46em,
      -0.82em -0.09em 0 -0.477em;
  }
  100% {
    box-shadow: 0 -0.83em 0 -0.4em, 0 -0.83em 0 -0.42em, 0 -0.83em 0 -0.44em,
      0 -0.83em 0 -0.46em, 0 -0.83em 0 -0.477em;
  }
}
@keyframes load6 {
  0% {
    box-shadow: 0 -0.83em 0 -0.4em, 0 -0.83em 0 -0.42em, 0 -0.83em 0 -0.44em,
      0 -0.83em 0 -0.46em, 0 -0.83em 0 -0.477em;
  }
  5%,
  95% {
    box-shadow: 0 -0.83em 0 -0.4em, 0 -0.83em 0 -0.42em, 0 -0.83em 0 -0.44em,
      0 -0.83em 0 -0.46em, 0 -0.83em 0 -0.477em;
  }
  10%,
  59% {
    box-shadow: 0 -0.83em 0 -0.4em, -0.087em -0.825em 0 -0.42em,
      -0.173em -0.812em 0 -0.44em, -0.256em -0.789em 0 -0.46em,
      -0.297em -0.775em 0 -0.477em;
  }
  20% {
    box-shadow: 0 -0.83em 0 -0.4em, -0.338em -0.758em 0 -0.42em,
      -0.555em -0.617em 0 -0.44em, -0.671em -0.488em 0 -0.46em,
      -0.749em -0.34em 0 -0.477em;
  }
  38% {
    box-shadow: 0 -0.83em 0 -0.4em, -0.377em -0.74em 0 -0.42em,
      -0.645em -0.522em 0 -0.44em, -0.775em -0.297em 0 -0.46em,
      -0.82em -0.09em 0 -0.477em;
  }
  100% {
    box-shadow: 0 -0.83em 0 -0.4em, 0 -0.83em 0 -0.42em, 0 -0.83em 0 -0.44em,
      0 -0.83em 0 -0.46em, 0 -0.83em 0 -0.477em;
  }
}
@-webkit-keyframes round {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(360deg);
    transform: rotate(360deg);
  }
}
@keyframes round {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(360deg);
    transform: rotate(360deg);
  }
}
</style>

