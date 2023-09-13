<template>
  <div class="mid">
  <div class="container">
    <div class="row">
      <img src="~assets/img/icon3.png" class="app-icon" />
      <img src="~assets/img/icon1.png" class="app-icon" />
      <img src="~assets/img/icon5.png" class="app-icon" />
    </div>  
    <div class="row">
      <img src="~assets/img/icon7.png" class="app-icon" />
      <img src="~assets/img/icon9.png" class="app-icon" />
      <img src="~assets/img/icon2.png" class="app-icon" />
    </div>
    <div class="row">
      <img src="~assets/img/icon10.png" class="app-icon" />
      <img src="~assets/img/icon8.png" class="app-icon" />
      <img src="~assets/img/icon6.png" class="app-icon" />
    </div>
    <div class="row">
      <img src="~assets/img/icon4.png" class="app-icon" />
      <img src="~assets/img/icon.png" class="homescreen-icon app-icon" @click="pressIcon" />
    
    </div>

  </div>

  <div class="dots">
      <span class="dot"></span>
      <span class="dot"></span>
      <span class="dot"></span>
    </div>
  </div>
  <Bottombar />
</template>
<script setup lang="ts">
const emit = defineEmits(['clicked', 'startClicked'])

const pressIcon = () => {
    emit('startClicked')
};
</script>
<style lang="scss" scoped>

.container {
  position: relative;
  margin: 24px 32px;
  width: 100%;
}

.row {
  display: flex;
  justify-content: space-between;
  gap: 24px;
  margin-right: 24px;
  margin-left: 24px;
  padding: 24px;
  height: 60px;

  &:first-of-type {
    margin-top: 32px;
    padding-top: 0;
  }

  &:last-of-type {
    padding-bottom: 0;
  }
}


img.app-icon {
  filter: drop-shadow(3px 3px 8px rgba(0,0,0,0.7));
}

.app-icon {
  width: 60px;
}

.dots {
  margin-top: auto;
  margin-bottom: 20px;
}
.dot {
  height: 10px;
  width: 10px;
    background-color: #444;
  border-radius: 50%;
  display: inline-block;
    margin-left: 8px;

  &:nth-of-type(2n+1) {
    background-color: rgba(150,150,150, 0.6);
  }
}
</style>
