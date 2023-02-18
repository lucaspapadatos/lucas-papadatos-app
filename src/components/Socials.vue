<script setup>
defineProps({});
</script>

<template>
  <div class="back">
    <img src="../assets/tv-lines-png-transparent.png" />
    SOCIALS
    <br />
    <a href="https://github.com/lucaspapadatos">GITHUB</a><br />
    <a href="https://www.linkedin.com/in/lucas-papadatos/">LINKEDIN</a>
  </div>
</template>

<style scoped>
a {
  color: white;
}
div {
  position: relative;
  right: 50%;
  color: white;
  width: 100%;
  height: 100%;
  background-image: linear-gradient(to top right, lightblue, magenta);
  background-size: cover;
}
img {
  position: absolute;
  width: 100%;
  height: 100%;
  left: 0;
  z-index: 1;
  pointer-events: none;
}
img::selection {
  background-color: transparent;
  color: #000;
}
</style>
