<script>
import Home from "./components/Home.vue";
import About from "./components/About.vue";
import Socials from "./components/Socials.vue";
import Projects from "./components/Projects.vue";
import Menu from "./components/Menu.vue";
import PanelLeft from "./components/PanelLeft.vue";
import PanelRight from "./components/PanelRight.vue";
import Game from "./components/Game.vue";
import Credits from "./components/Credits.vue";

export default {
  data() {
    return {
      select: 1,
      on: false,
      mute: false,
      started: false,
      showCredits: false,
    };
  },
  methods: {},
  components: {
    Home,
    About,
    Socials,
    Projects,
    Menu,
    PanelLeft,
    PanelRight,
    Game,
    Credits,
  },
};
</script>

<template>
  <body>
    <div class="container">
      <transition name="credits">
        <div v-if="showCredits == true" class="credits">
          <Credits></Credits>
        </div>
      </transition>
      <PanelLeft class="left-container"></PanelLeft>
      <PanelRight class="right-container"></PanelRight>
      <button v-on:click="showCredits = !showCredits" class="credits-button">
        Credits
      </button>
      <div class="console">
        <img
          class="ds"
          alt="DSi"
          src="./assets/DSi_White.png"
          draggable="false"
        />
        <Home class="top-container" v-if="select == 1 && on == true"></Home>
        <About class="top-container" v-if="select == 2 && on == true"></About>
        <Socials
          class="top-container"
          v-if="select == 3 && on == true"
        ></Socials>
        <Projects
          class="top-container"
          v-if="select == 4 && on == true"
        ></Projects>
        <div class="bot-container">
          <Menu :muted="mute" v-if="on == true"></Menu>
          <Game v-else-if="started == true"></Game>
        </div>
        <button
          class="power-but"
          v-on:click="(started = false) & (on = !on)"
        ></button>
        <button class="b1" v-on:click="select = 1"></button>
        <button class="b2" v-on:click="select = 2"></button>
        <button class="b3" v-on:click="select = 3"></button>
        <button class="b4" v-on:click="select = 4"></button>
        <button
          class="start-but"
          v-on:click="(started = true) & (on = false)"
        ></button>
        <button class="mute-but" v-on:click="mute = !mute"></button>
        <div>
          <img class="mute-text" src="./assets/mute.png" />
          <img class="mute-bg" src="./assets/blend.png" />
          <img class="start-text" src="./assets/start.png" />
          <img class="start-bg" src="./assets/blend.png" />
          <img class="power-text" src="./assets/power.png" />
          <img class="power-bg" src="./assets/blendleft.png" />
        </div>
      </div>
    </div>
  </body>
</template>

<style scoped>
.credits {
  width: 80%;
  height: 80%;
}
.credits-enter-active,
.credits-leave-active {
  transition: all 0.25s;
}

.credits-enter-to,
.credits-leave {
  transform: translateX(75%);
}
.credits-button {
  position: absolute;
  bottom: 50%;
  right: 5%;
  color: white;
}
.mute-text {
  position: absolute;
  z-index: 1;
  bottom: 6.7%;
  right: 9.9%;
  width: 5%;
  height: 1.5%;
}
.start-text {
  position: absolute;
  z-index: 1;
  bottom: 12.3%;
  right: 8.9%;
  width: 6%;
  height: 1.5%;
}
.power-text {
  position: absolute;
  z-index: 1;
  bottom: 6.9%;
  left: 9.9%;
  width: 5%;
  height: 1.5%;
}
.mute-bg {
  position: absolute;
  bottom: 5.6%;
  right: 6.4%;
  width: 10%;
  height: 5%;
}
.start-bg {
  position: absolute;
  bottom: 10.6%;
  right: 6.4%;
  width: 10%;
  height: 5%;
}
.power-bg {
  position: absolute;
  bottom: 6%;
  left: 6.5%;
  width: 10%;
  height: 5%;
}
.mute-but {
  bottom: 5.9%;
  right: 17%;
  width: 3.3%;
  height: 3.3%;
}
.start-but {
  bottom: 11.5%;
  right: 17%;
  width: 3.3%;
  height: 3.3%;
}
.power-but {
  bottom: 5.9%;
  left: 17%;
  width: 3.3%;
  height: 3.3%;
  border-color: gainsboro;
}
.b1 {
  /* X */
  bottom: 34.4%;
  right: 9%;
  width: 5.5%;
  height: 5.5%;
}
.b2 {
  /* A */
  bottom: 29%;
  right: 3.4%;
  width: 5.5%;
  height: 5.5%;
}
.b3 {
  /* B */
  bottom: 23.7%;
  right: 8.9%;
  width: 5.5%;
  height: 5.5%;
}
.b4 {
  /* Y */
  bottom: 29%;
  right: 14.4%;
  width: 5.5%;
  height: 5.5%;
}
button {
  position: absolute;
  cursor: pointer;
  background-color: transparent;
  border-radius: 50%;
}
button:active {
  background-color: grey;
  opacity: 50%;
}
.ds {
  height: 100%;
  width: 100%;
}
.container {
  background: url("./assets/spaceboy.gif") no-repeat center center fixed;
  height: 100vh;
  width: 100%;
  position: relative;
}
.console {
  text-align: center;
  height: auto;
  width: 50%;
  min-height: 300px;
  min-width: 300px;
  margin: 0 auto;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 1;
}
.top-container {
  width: 47.9%;
  height: 35.2%;
  position: absolute;
  top: 6.2%;
  left: 26.3%;
}
.bot-container {
  width: 47.9%;
  height: 35.2%;
  position: absolute;
  bottom: 6.6%;
  left: 26.3%;
}
img::selection {
  background-color: transparent;
  color: #000;
}
img {
  pointer-events: none;
}
.left-container {
  position: absolute;
  bottom: 20%;
  left: 5%;
}
.right-container {
  position: absolute;
  bottom: 20%;
  right: 5%;
}
</style>
