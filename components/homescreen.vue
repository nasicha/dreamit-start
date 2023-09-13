<template>
  <div class="mid">
    <img src="~assets/img/icon.png" class="homescreen-icon app-icon" :class="{pressed: pressed}" @click="pressIcon" />

    <div class="dots">
      <span class="dot"></span>
      <span class="dot"></span>
    </div>
  </div>
  <Bottombar />
</template>
<script setup lang="ts">
const pressed = ref(false);
const emit = defineEmits(['clicked', 'startClicked'])

const pressIcon = () => {
  pressed.value = !pressed.value;

  setTimeout(() => {
    emit('startClicked')
  }, 0);
};
</script>
<style lang="scss" scoped>
.app-icon {
  width: 80px;
  // filter: drop-shadow(-2px 2px 5px rgba(0,0,0,0.5));
}

.homescreen-icon {
  position: relative;
  margin-top: 50%;
  transform-origin: center center 0px;
  transform: matrix(1, 0, 0, 1, 0, 0);
}

.homescreen-icon .pressed {
    transform: matrix(0.95, 0, 0, 0.95, 0, 0);
}

.dots {
  margin-top: auto;
  margin-bottom: 20px;
}
.dot {
  height: 10px;
  width: 10px;
  background-color: rgba(150,150,150, 0.6);
  border-radius: 50%;
  display: inline-block;

  &:first-of-type {
    margin-right: 8px;
    background-color: #444;
  }
}
</style>
