<template>
  <img src="~assets/img/backgroundImage.jpeg" class="homescreen-background" />
  <div class="mid">
    <img src="~assets/img/icon.jpeg" class="homescreen-icon" @click="$emit('startClicked')" />
  </div>
</template>
<script setup lang="ts">
</script>
<style lang="scss">
.homescreen {
  &-background {
    position: absolute;
    height: 110vh;
    object-fit: cover;
    top: -5vh;
    filter: blur(8px);
    -webkit-filter: blur(2px);
  }

  &-icon {
    width: 80px;
    margin-top: 50%;
  }
}

</style>
