<template>
  <div class="video-wrapper">
    <Transition name="fadelong">
    <div v-if="!startApp">
      <video src="~assets/video/appstart.mp4" class="app-start" autoplay muted loop>
          <p>Your browser does not support the video tag.</p>
      </video>
    </div>
    </Transition>
      <video src="~assets/video/bgWaves.mp4" class="app-bg" autoplay muted>
          <p>Your browser does not support the video tag.</p>
      </video>
  </div>
</template>
<script setup lang="ts">
import gsap from "gsap";
defineProps({startApp: Boolean})

setTimeout(() => {
  gsap.to(".app-start", {
    duration: .2,
    ease: "power4.out",
    opacity: 0,
  });
}, 2000);

</script>
<style lang="scss" scoped>
.video-wrapper {
  position: absolute;
  width: 100vw;
  height: 100%;
  z-index: 0;

  div {
    position: relative;
    width: inherit;
    height: inherit;
  }
}

.app {
  &-start, &-bg  {
    position: absolute;
    width: 100%;
    height: 100%;
    object-fit: cover;
    top: 0;
  }

  &-start {
    z-index: 1;
  }
  &-bg {
    z-index: 0;
  }
}

</style>