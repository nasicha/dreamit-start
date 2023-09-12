<template>
  <div class="mid">
    <img src="~assets/img/icon.png" class="homescreen-icon" @click="$emit('startClicked')" />
  </div>
</template>
<script setup lang="ts">
</script>
<style lang="scss">
.homescreen {

  &-icon {
    width: 80px;
    margin-top: 50%;
  }
}

</style>
