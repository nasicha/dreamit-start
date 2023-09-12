<template>
  <div class="video-wrapper">
    <video v-if="!startApp" src="~assets/video/appstart.mp4" autoplay muted loop>
        <p>Your browser does not support the video tag.</p>
    </video>
    <video src="~assets/video/bgWaves.mp4" :class="{hideVideo: !startApp}" autoplay muted>
        <p>Your browser does not support the video tag.</p>
    </video>
  </div>
</template>
<script setup lang="ts">
import gsap from "gsap";

defineProps({startApp: Boolean})




</script>
<style lang="scss" scoped>
.video-wrapper {
  position: absolute;
  width: 100vw;
  height: 100%;
  z-index: 0;

  video {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
}

.hideVideo {
  display: none;
}

</style>