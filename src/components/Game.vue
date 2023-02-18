<script>
export default {
  props: {
    muted: {
      type: Boolean,
      required: true,
    },
  },
  mounted() {
    this.$refs.audio.volume = 0.1;
  },
};
</script>

<template>
  <div>
    <object data="https://creative.caslab.queensu.ca/~GDP9/"></object>
  </div>
</template>

<style scoped>
object {
  border: none;
  width: f;
  height: max-content;
}
div {
  border: red 1px solid;
  color: white;
  width: 100%;
  height: 100%;
  overflow: hidden;
}
img {
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 1;
  pointer-events: none;
}
img::selection {
  background-color: transparent;
  color: #000;
}
video {
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 0;
  pointer-events: none;
}
audio {
  width: 0%;
}
</style>
