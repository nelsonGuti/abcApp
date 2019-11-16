<template>
  <div>
    <div class="card-block">
      <select v-model="selected">
        <option v-for="shape in shapes" :key="shape.id">{{shape.name}}</option>
      </select>
      <div class="card-wrapper">
        <Shape class="item" :shape="selectedShape"></Shape>
      </div>
    </div>
  </div>
</template>

<script>
import Shape from "./Shape.vue";

export default {
  name: "CardContainer",
  components: {
    Shape
  },
  props: {
    shapes: {
      type: Array
    }
  },
  computed: {
    selectedShape: function() {
      return this.shapes.find(({ name }) => name === this.selected);
    }
  },
  data() {
    return {
      selected: "Circle"
    };
  },
  methods: {
    /* selectedShape2: function() {
      return this.shapes.find(({ name }) => (name = this.selected));
    } */
  }
};
</script>

<style scoped>
select {
  padding: 0.5rem;
  width: 175px;
  font-family: "Montserrat", sans-serif;
  text-align-last: center;
  font-size: 1rem;
  margin-bottom: 1.25rem;
}
.card-wrapper {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(275px, 1fr));
  grid-gap: 25px;
}

@media (max-width: 750px) {
  select {
    width: 75%;
  }

  .card-wrapper {
    margin: 0 24px;
  }
}
</style>

