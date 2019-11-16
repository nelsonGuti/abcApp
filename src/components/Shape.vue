<template>
  <div>
    <div class="shape-grid">
      <div class="item border">{{shape.name}}</div>
      <div class="item shape">
        <div :class="shape.class"></div>
      </div>
      <div class="item border">{{shape.nombre}}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Shape",
  props: {
    shape: {
      type: Object
    }
  }
};
</script>

<style >
.shape-grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  justify-content: center;
  align-content: center;
  row-gap: 25px;
  height: 35vh;
  box-shadow: 0 14px 28px rgba(0, 0, 0, 0.25), 0 10px 10px rgba(0, 0, 0, 0.22);
  border-radius: 5%;
  width: 100%;

  background-color: #fff;
  opacity: 1;
}

.item.shape {
  width: 125px;
}

.circleShape {
  width: 100px;
  height: 100px;
  background: #2c3e50;
  border-radius: 50%;
}

.triangleShape {
  width: 0;
  height: 0;
  border-left: 50px solid transparent;
  border-right: 50px solid transparent;
  border-bottom: 100px solid #2c3e50;
}
.squareShape {
  width: 100px;
  height: 100px;
  background: #2c3e50;
}
.rectangleShape {
  width: 100px;
  height: 60px;
  background: #2c3e50;
}

.ovalShape {
  width: 120px;
  height: 60px;
  background: #2c3e50;
  border-radius: 100px / 50px;
}

.starShape {
  width: 0;
  height: 0;
  border-left: 50px solid transparent;
  border-right: 50px solid transparent;
  border-bottom: 100px solid #2c3e50;
  position: relative;
}
.starShape:after {
  width: 0;
  height: 0;
  border-left: 50px solid transparent;
  border-right: 50px solid transparent;
  border-top: 100px solid #2c3e50;
  position: absolute;
  content: "";
  top: 30px;
  left: -50px;
}
</style>