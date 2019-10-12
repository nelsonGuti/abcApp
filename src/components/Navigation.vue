<template>
  <div>
    <ul>
      <li
        v-for="(icon, index) in navIcons"
        :key="index"
        @click="getSelection(icon)"
        :class="{active : menuSelection === icon[1]}"
      >
        <font-awesome-icon :icon="icon[0]" />
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Navigation",
  props: {
    navIcons: {
      type: Array,
      required: true
    }
  },
  data: function() {
    return {
      menuSelection: "letters"
    };
  },
  methods: {
    getSelection(icon) {
      this.menuSelection = icon[1];
      this.$emit("selectionState", this.menuSelection);
    }
  }
};
</script>

<style>
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  font-size: 8rem;
  padding: 1.5rem 1.5rem 0.5rem 1.5rem;
}
li svg {
  color: rgb(2, 63, 5);
  background-color: rgb(179, 212, 187);
  padding: 1.25rem;
  border-radius: 10%;
}
.active {
  border-bottom: 1px solid rgb(2, 63, 5);
}

@media (max-width: 650px) {
  li {
    font-size: 3rem;
    padding: 0.5rem;
  }
  li svg {
    padding: 0.75rem;
  }
}
</style>