<template>
  <div class="video-wrapper">
  <Transition name="fade">
    <video v-if="!startApp" src="~assets/video/appstart.mp4" autoplay muted loop>
        <p>Your browser does not support the video tag.</p>
    </video>
  </Transition>
    <video src="~assets/video/bgWaves.mp4" autoplay muted>
        <p>Your browser does not support the video tag.</p>
    </video>
  </div>
</template>
<script setup lang="ts">
const props = defineProps({startApp: Boolean})


</script>
<style lang="scss" scoped>
.video-wrapper {
  position: absolute;
  width: 100vw;
  height: 100vh;
  z-index: -1;

  video {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.2s reverse;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>