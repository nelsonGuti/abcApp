<template>
  <div>
    <div class="numbers-block">
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
          <Fireworks></Fireworks>
          <button @click="reset">
            <font-awesome-icon :icon="icon" />
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import NumberItem from "./NumberItem.vue";
import Fireworks from "./Fireworks.vue";
import { faRedo } from "@fortawesome/free-solid-svg-icons";
export default {
  name: "Numbers",
  components: {
    NumberItem,
    Fireworks
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
      selected: 1,
      icon: faRedo
    };
  },
  methods: {
    increment() {
      this.selected = this.selected + 1;
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

button {
  color: rgb(2, 63, 5);
  background-color: rgb(179, 212, 187);
  padding: 1.25rem;
  border-radius: 10%;
  font-size: 2rem;
  border: none;
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