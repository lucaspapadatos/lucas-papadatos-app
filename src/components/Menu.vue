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
    <video controls loop autoplay muted>
      <source src="../assets/cyber.mp4" type="video/mp4" />
      Your browser does not support the video element
    </video>
    <img src="../assets/tv-lines-png-transparent.png" />
  </div>
  <audio ref="audio" controls loop autoplay v-bind:muted="muted">
    <source src="../assets/.mp3" type="audio/mpeg" />
    Your browser does not support the audio element.
  </audio>
</template>

<style scoped>
div {
  position: relative;
  right: 50%;
  color: white;
  width: 100%;
  height: 100%;
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
