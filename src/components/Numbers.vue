<template>
  <div>
    <div class="numbers-block">
      <!-- <select v-model="selected">
        <option>1 - 9</option>
        <option v-for="number in numbers" :key="number.id">{{number.id}}</option>
      </select>-->
      <!-- {{this.selected}} -->
      <div class="numbers-wrapper">
        <NumberItem
          @allCirclesClicked="increment"
          class="item"
          :number="number"
          :selected="selected"
          v-for="number in selectedNumber"
          :key="number.id"
        ></NumberItem>
        <div v-if="selected > numbers.length">
          <button @click="reset">Retry</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import NumberItem from "./NumberItem.vue";
export default {
  name: "Numbers",
  components: {
    NumberItem
  },
  props: {
    numbers: {
      type: Array
    }
  },
  computed: {
    selectedNumber: function() {
      return this.numbers.filter(number => number.id === Number(this.selected));
    }
  },
  data() {
    return {
      selected: 1
    };
  },
  methods: {
    getNumber() {
      return this.selected === "1 - 9" ? this.numbers : this.selectedNumber;
    },
    increment() {
      this.selected = this.selected + 1;
      // console.log("this.selected: ", this.selected);
    },
    reset() {
      this.selected = 1;
    }
  }
};
</script>

<style>
select {
  padding: 0.5rem;
  width: 175px;
  font-family: "Montserrat", sans-serif;
  text-align-last: center;
  font-size: 1rem;
  margin-bottom: 2rem;
}
.numbers-wrapper {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(275px, 1fr));
  grid-gap: 25px;
}

.numbers-block {
  margin-top: 5rem;
}

@media (max-width: 750px) {
  select {
    width: 75%;
  }
  .numbers-wrapper {
    margin: 0 24px;
  }
}
</style>