<template>
  <div class="video-wrapper-startdream">
    <video ref="video">
      <source src="~assets/video/gutenacht.mp4" type="video/mp4" />
        <p>Your browser does not support the video tag.</p>
    </video>
    <Transition name="fadelong">
      <div v-if="showOverlay" class="overlay" />
    </Transition>
  </div>
</template>
<script setup lang="ts">
const video = ref(null);
const showOverlay = ref(false);
onMounted(() => {
  if (video.value) {
    video.value.play();
  }


  setTimeout(() => {
    showOverlay.value = true;
  }, 6500);

});

</script>
<style lang="scss">
.video-wrapper-startdream {
  position: relative;
  top: -5vh;
  width: 100vw;
  height: 100vh;
  z-index: 20;

  video {
    position: absolute;
    width: 100%;
    height: 100%;
    object-fit: cover;
    top: 0;
    z-index: 15;
    left: 0;
    right: 0;
    margin-left: auto;
    margin-right: auto;
  }

  .overlay {
    position: absolute;
    width: 100%;
    height: 100%;
    background-color: #121212;
    z-index: 16;
  }
}

.fadelong-enter-active,
.fadelong-leave-active {
  transition: opacity 1s;
}

.fadelong-enter-from,
.fadelong-leave-to {
  opacity: 0;
}
</style>