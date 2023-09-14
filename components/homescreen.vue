<template>
  <div class="mid">
  <div class="container">
    <div class="row">
    <div>
      <img src="~assets/img/icon3.png" class="app-icon" />
      <span>{{ truncate(names[3]) }}</span>
    </div>
    <div>
      <img src="~assets/img/icon1.png" class="app-icon" />
      <span>{{ truncate(names[1]) }}</span>
    </div>
    <div>
      <img src="~assets/img/icon5.png" class="app-icon" />
      <span>{{ truncate(names[5]) }}</span>
    </div>
    </div>  
    <div class="row">
    <div>
      <img src="~assets/img/icon7.png" class="app-icon" />
      <span>{{ truncate(names[7]) }}</span>
    </div>
    <div>
      <img src="~assets/img/icon9.png" class="app-icon" />
      <span>{{ truncate(names[9]) }}</span>
    </div>
    <div>
      <img src="~assets/img/icon2.png" class="app-icon" />
      <span>{{ truncate(names[2]) }}</span>
    </div>
    </div>
    <div class="row">
    <div>
      <img src="~assets/img/icon10.png" class="app-icon" />
      <span>{{ truncate(names[10]) }}</span>
    </div>
    <div>
      <img src="~assets/img/icon8.png" class="app-icon" />
      <span>{{ truncate(names[8]) }}</span>
    </div>
    <div>
      <img src="~assets/img/icon6.png" class="app-icon" />
      <span>{{ truncate(names[6]) }}</span>
    </div>
    </div>
    <div class="row">
    <div>
      <img src="~assets/img/icon4.png" class="app-icon" />
      <span>{{ truncate(names[4]) }}</span>
    </div>
    <div>
      <div class="app-icon" />
    </div>
    <div @click="pressIcon" >
      <img src="~assets/img/icon.png" class="homescreen-icon app-icon" />
      <span>{{ truncate(names[11]) }}</span>
    </div>
    
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

const names = {
  '1': 'Example',
  '2': 'skillz',
  '3': 'Tide Art',
  '4': 'Act Up',
  '5': 'RSM Retro',
  '6': 'Origami',
  '7': 'ThreeSpace',
  '8': 'PiChat',
  '9': 'Columns',
  '10': 'Ex Aequo',
  '11': 'Dreamit',
}

const truncate = (str: string, n = 10) => {
  return (str.length > n) ? str.substr(0, n-1) + '...' : str;
}
</script>
<style lang="scss" scoped>

.container {
  position: relative;
  margin: 24px 24px;
  width: 100%;
}

.row {
  display: flex;
  justify-content: space-between;
  margin-right: 24px;
  margin-left: 24px;
  padding: 38px 0 0;
  height: 88px;

  &:first-of-type {
    margin-top: 32px;
    padding-top: 0;
  }

  &:last-of-type {
    padding-bottom: 0;
  }

  & > div {
    text-align: center;
    display: flex;
    flex-direction: column;
    height: 88px;
    width: 88px;
    justify-content: space-between;
    align-items: center;


    & > span {
      color: white;
      font-size: 12px;
      filter: drop-shadow(0 0 2px rgba(0,0,0,0.5));
    }
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
