<template>
  <div>
    <div class="header">
      <p class="subheader">App that helps you learn your letters, numbers and shapes 😉</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Header"
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.a {
  color: rgb(22, 22, 121);
  font-size: 8rem;
}

.b {
  color: red;
  font-size: 8rem;
}

.c {
  color: rgb(18, 197, 63);
  font-size: 8rem;
}

.header {
  padding: 0 2.5vw;
}
@media (max-width: 750px) {
  .a,
  .b,
  .c {
    font-size: 4rem;
  }
}
</style>
