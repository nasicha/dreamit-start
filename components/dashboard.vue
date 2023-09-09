<template>
  <Transition name="fade">
    <StartDream v-if="start" />
  </Transition>
  <div class="mid">
    <Menu class="menu" />
    <img src="~assets/img/half-circle.png" class="circle" />
    <img src="~assets/img/luna.png" class="luna" />
    <h2>Luna's Dream</h2>
    <h3>PREMIUM</h3>    
    <div class="mid-btn">
      <img src="~assets/img/GLOW.png" class="glow" />
      <img src="~assets/img/dream-btn.png" class="dream-btn" @click="startDream" />
    </div>  
  </div>
  <div class="bottom">
    <Home />
    <Category />
    <Profile />
  </div>
</template>
<script setup lang="ts">
import Menu from "@/assets/img/menu.svg?component";
import Home from "@/assets/img/home.svg?component";
import Profile from "@/assets/img/profile.svg?component";
import Category from "@/assets/img/category.svg?component";

const start = ref(false);

const startDream = () => {
  start.value = true;
};


</script>
<style lang="scss">
$base-color: rgb(3, 19, 65);

.menu {
  position: absolute;
  z-index: 12;
  left: 7vw;
}
.circle {
  position: absolute;
  width: 105vw;  
  fill: $base-color;
  top: -11%;
  left: 50%;
  transform: translateX(-50%);
  z-index: 11;
}

.luna {
  position: relative;
  margin-top: 20px;
  width: 160px;
  z-index: 12;
}
.mid-btn {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  z-index: 12;
}
.dream-btn {
  width: 200px;
  margin-top: 80px;
  z-index: 12;
}

.glow {
  width: 300px;
  height: 300px;
  position: absolute;
  z-index: 5;
  top: 35px;
  transform: scale(1);
  animation: pulse 1.5s infinite;
}

.bottom {
  background-color: $base-color;
  z-index: 15;
  display: flex;
  justify-content: space-around;
  align-items: center;
}

@keyframes pulse {
  0% {
    transform: scale(0.9);
  }

  50% {
    transform: scale(1);
  }

  100% {
    transform: scale(0.9);
  }
}
</style>
