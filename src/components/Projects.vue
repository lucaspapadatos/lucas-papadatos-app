<script setup>
defineProps({});
</script>

<template>
  <div class="back">
    <img src="../assets/tv-lines-png-transparent.png" />
    PROJECTS
    <br />
    <a href="https://github.com/lucaspapadatos/monkey-marathon"
      >GAME DEV Project</a
    ><br />
    <a href="https://github.com/lucaspapadatos/CISC327-Project">QA Project</a>
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
