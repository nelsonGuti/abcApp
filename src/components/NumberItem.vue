<template>
  <div>
    <div class="number-grid">
      <div class="item id">{{number.id}}</div>
      <div class="item circles">
        <div v-for="(number,index) in currentNumber" :key="index" class="circle"></div>
      </div>
      <div class="item names">
        <div class="number-item-name">{{number.name}}</div>
        <div class="number-item-name">{{number.nombre}}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Number-Item",
  computed: {
    currentNumber: function() {
      // console.log(Array(this.number).fill(1));
      return Array(this.number.id).fill(1);
    }
  },
  props: {
    number: {
      type: Object
    }
  }
};
</script>

<style>
.number-grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  justify-content: center;
  align-content: center;
  row-gap: 25px;
  height: 35vh;
  box-shadow: 0 14px 28px rgba(0, 0, 0, 0.25), 0 10px 10px rgba(0, 0, 0, 0.22);
  border-radius: 5%;
  width: 100%;
}

.item {
  display: grid;
  justify-content: center;
  align-content: center;
}

.item.id {
  font-size: 5rem;
}

.item.names {
  display: grid;
  grid-template-rows: 1fr 1fr;
  font-size: 1rem;
}

.number-item-name {
  display: grid;
  justify-content: center;
  align-content: center;
}

.item.circles {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(35px, 1fr));
  row-gap: 25px;
  width: 125px;
}
.circle {
  height: 15px;
  width: 15px;
  border-radius: 50%;
  background-color: #2c3e50;
  display: grid;
  align-self: center;
  justify-self: center;
}
</style>
