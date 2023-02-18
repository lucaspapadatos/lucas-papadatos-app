<script setup>
defineProps({});
</script>

<template>
  <div>
    ABOUT
    <img class="bg" src="../assets/tv-lines-png-transparent.png" />
    <img class="pfp" src="../assets/saw.jpg" />
  </div>
</template>

<style scoped>
div {
  position: relative;
  right: 50%;
  color: white;
  width: 100%;
  height: 100%;
  background-image: linear-gradient(to bottom, black, red);
  background-size: cover;
}
.bg {
  position: absolute;
  width: 100%;
  height: 100%;
  left: 0;
  z-index: 1;
  pointer-events: none;
}
.pfp {
  position: absolute;
  left: 10%;
  top: 12%;
  pointer-events: none;
  width: 12%;
  height: 15%;
}
img::selection {
  background-color: transparent;
  color: #000;
}
</style>
