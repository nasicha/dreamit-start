<template>
  <Transition name="fadelong">
    <StartDream v-if="start" />
  </Transition>
  <div v-if="!start" class="mid">
    <Menu class="menu" id="menu" />
    <img src="~assets/img/half-circle.png" class="circle" id="halfCircle"/>
    <img src="~assets/img/luna.png" class="luna" id="luna" />
    <h2 id="lunaDream">Luna's Dream</h2>
    <h3 id="premium">PREMIUM</h3>    
    <div class="mid-btn" id="btn" >
      <img src="~assets/img/GLOW.png" class="glow" :class="{animateGlow: animateGlow}" />
      <img src="~assets/img/dream-btn.png" class="dream-btn" :class="{pressed: pressed}" @click="startDream" />
    </div>  
  </div>
  <div v-if="!start" class="bottom" id="bottom">
    <Home />
    <Category />
    <Profile />
  </div>
</template>
<script setup lang="ts">
import gsap from "gsap";
import Menu from "@/assets/img/menu.svg?component";
import Home from "@/assets/img/home.svg?component";
import Profile from "@/assets/img/profile.svg?component";
import Category from "@/assets/img/category.svg?component";

const start = ref(false);
const pressed = ref(false);
const animateGlow = ref(false);

const startDream = () => {
  pressed.value = !pressed.value;
  setTimeout(() => {
    pressed.value = !pressed.value;
  }, 100);
  setTimeout(() => {
    start.value = true;
  }, 250);
};


const firstElementDuration = 0.5;
const delayedElementDuration = 0.75;
const firstDelay = 250;
const delay = 100;

onMounted(() => {
  gsap.to("#halfCircle", {
    duration: firstElementDuration,
    ease: "power4.out",
    top: "-11%",
  });

  gsap.to("#bottom", {
    duration: firstElementDuration,
    ease: "power4.out",
    marginTop: "0",
  });

  setTimeout(() => {
    gsap.to("#luna", {
      duration: delayedElementDuration,
      ease: "power4.out",
      scale: "1",
    });
    gsap.to("#menu", {
      duration: delayedElementDuration,
      ease: "power4.out",
      scale: "1",
    });
  }, firstDelay);

  setTimeout(() => {
    gsap.to("#lunaDream", {
      duration: delayedElementDuration,
      ease: "power4.out",
      opacity: "1"
    });
    gsap.to("#premium", {
      duration: delayedElementDuration,
      ease: "power4.out",
      opacity: "1"
    });
    
  }, firstDelay+delay);

  setTimeout(() => {
    gsap.to("#btn", {
      duration: delayedElementDuration,
      ease: "power4.out",
      scale: "1",
    });
  }, firstDelay+delay*2);

  setTimeout(() => {
    animateGlow.value = true;
  }, 100+firstDelay+delay*2);
});

</script>
<style lang="scss">
$base-color: rgb(3, 19, 65);

.menu {
  position: absolute;
  z-index: 12;
  left: 7vw;
  scale: 0;
}
.circle {
  position: absolute;
  width: 105vw;  
  fill: $base-color;
  top: -20%;
  left: 50%;
  transform: translateX(-50%);
  z-index: 11;
}

.luna {
  position: relative;
  margin-top: 20px;
  width: 160px;
  z-index: 12;
  scale: 0;
}
.mid-btn {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  z-index: 12;
  scale: 0;
  transition-duration: .2s;
  transform-origin: center center 0px;
  transform: matrix(1, 0, 0, 1, 0, 0);

  & .pressed {
    transform: matrix(0.95, 0, 0, 0.95, 0, 0);
  }
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

}
.animateGlow {
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
