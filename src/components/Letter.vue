<template>
  <div>
    <div class="letter">
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
        <div class="lds-hourglass"></div>
      </div>
      <div class="item" v-else-if="errored">Could not find the picture</div>

      <div class="item">
        <p v-for="(word,index) in letter.words" :key="index">{{word}}</p>
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
      toggleCase: false
    };
  },
  computed: {
    imageLoaded: function() {
      return this.image;
    }
  },
  mounted() {
    axios
      .get(this.letter.img)
      .then(response => {
        this.image = response.config.url;
      })
      .catch(error => {
        console.log(error);
        this.errored = true;
      })
      .finally(() => (this.loading = false));
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
/* h1:hover {
  text-transform: uppercase;
  color: tomato;
} */

.toggleCase {
  color: rgb(185, 28, 125);
  text-transform: uppercase;
}
.letter {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  height: 35vh;
  box-shadow: 0 14px 28px rgba(0, 0, 0, 0.25), 0 10px 10px rgba(0, 0, 0, 0.22);
  row-gap: 50px;
}
.item {
  display: grid;
  justify-content: center;
  align-content: center;
}

.item.loading {
  min-width: 150px;
}

.imageLoaded {
  border-radius: 50%;
  grid-area: 1 / 1;
}

.placeholder {
  background-color: white;
  width: 150px;
  height: 150px;
  border-radius: 50%;
  grid-area: 1 / 1;
}

.lds-hourglass {
  display: inline-block;
  position: relative;
  width: 64px;
  height: 64px;
}
.lds-hourglass:after {
  content: " ";
  display: block;
  border-radius: 50%;
  width: 0;
  height: 0;
  margin: 6px;
  box-sizing: border-box;
  border: 26px solid rgb(185, 28, 125);
  border-color: rgb(185, 28, 125) transparent rgb(185, 28, 125) transparent;
  animation: lds-hourglass 1.2s infinite;
}
@keyframes lds-hourglass {
  0% {
    transform: rotate(0);
    animation-timing-function: cubic-bezier(0.55, 0.055, 0.675, 0.19);
  }
  50% {
    transform: rotate(900deg);
    animation-timing-function: cubic-bezier(0.215, 0.61, 0.355, 1);
  }
  100% {
    transform: rotate(1800deg);
  }
}
</style>

