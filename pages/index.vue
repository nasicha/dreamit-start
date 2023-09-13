<template>
  <div class="page">
    <img src="~assets/img/backgroundImage.jpeg" class="page-background" />
    <Transition name="bounce">
      <Background v-if="startClicked" :startApp="toggleDashboard" />
    </Transition>
    <div class="top" :class="{'top--hide': startClicked}">
      <SmartphoneTopbar />
    </div>
    <Dashboard v-if="toggleDashboard" />
    <Homescreen v-if="!startClicked" @start-clicked="toggleStartClicked" />
  </div>
</template>
<script setup lang="ts">
import SmartphoneTopbar from "@/assets/img/smartphone-topbar.svg?component";

const toggleDashboard = ref(false);

const startClicked = ref(false);

const toggleStartClicked = () => {
  startClicked.value = true;

  setTimeout(() => {
    toggleDashboard.value = true;
  }, 2200);
};


useHead({
  title: "DreamIt - App Start",
  link: [
    {
      rel: "preload",
      as: "video",
      href: "../assets/video/bgWaves.mp4",
      type: "video/mp4",
    },
    {
      rel: "preload",
      as: "video",
      href: "../assets/video/appstart.mp4",
      type: "video/mp4",
    },
    {
      rel: "preload",
      as: "video",
      href: "../assets/video/gutenacht.mp4",
      type: "video/mp4",
    }
  ],
});
</script>
<style lang="scss">
@use '../assets/scss/page.scss';
@use '../assets/scss/transition.scss';



</style>