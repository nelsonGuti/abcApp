<template>
  <div>
    <div class="letter">
      <div class="item">
        <h1>{{letter.name}}</h1>
      </div>
      <div class="image">
        <img :src="letter.img" alt>
      </div>
      <div class="item">
        <p v-for="(word,index) in letter.words" :key="index">{{word}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Letter",
  props: {
    letter: {
      type: Object
    }
  }
};
</script>

<style scoped>
h1 {
  font-size: 4rem;
}
h1:hover {
  text-transform: uppercase;
  color: tomato;
}
.letter {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  height: 35vh;
  /*border: 1px solid #2c3e50;*/
  box-shadow: 0 14px 28px rgba(0, 0, 0, 0.25), 0 10px 10px rgba(0, 0, 0, 0.22);
  row-gap: 50px;
}
.item {
  display: grid;
  justify-content: center;
  align-content: center;
}

.words p:hover {
  color: rgb(172, 20, 108);
  text-transform: uppercase;
}

.image {
  display: grid;
  align-self: center;
  justify-self: center;
}

.image img {
  border-radius: 50%;
}
</style>

