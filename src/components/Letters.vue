<template>
  <div>
    <div class="letter-block">
      <select v-model="selected">
        <option>All</option>
        <option>Vowels</option>
        <option>Consonants</option>
        <option v-for="letter in letters" :key="letter.id">{{letter.name}}</option>
      </select>
      <!-- <p>{{selected}}</p> -->
      <div class="letter-wrapper">
        <Letter class="item" :letter="letter" v-for="letter in selectedValue()" :key="letter.id"></Letter>
      </div>
    </div>
  </div>
</template>

<script>
import Letter from "./Letter.vue";

export default {
  name: "Letters",
  components: {
    Letter
  },
  props: {
    letters: {
      type: Array
    }
  },
  computed: {
    vowels: function() {
      return this.letters.filter(i => i.vocal);
    },
    consonants: function() {
      return this.letters.filter(i => !i.vocal);
    }
  },
  data() {
    return {
      selected: "All"
    };
  },
  methods: {
    getLetter(arr, search) {
      return arr.filter(i => i.name === search.toLowerCase())[0];
    },
    selectedValue() {
      const filteredData = {
        All: this.letters,
        Vowels: this.vowels,
        Consonants: this.consonants
      };

      return filteredData[this.selected]
        ? filteredData[this.selected]
        : this.letters.filter(i => i.name === this.selected.toLowerCase());
    }
  }
};
</script>

<style scoped>
/* .item {
  max-width: 650px;
} */
select {
  padding: 0.5rem;
  width: 175px;
  font-family: "Montserrat", sans-serif;
  text-align-last: center;
  font-size: 1rem;
  margin-bottom: 2rem;
}
.letter-wrapper {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  grid-gap: 25px;
}

@media (max-width: 750px) {
  select {
    width: 75%;
  }
}
</style>

