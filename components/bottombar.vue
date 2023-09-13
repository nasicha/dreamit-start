<template>
  <div class="bottombar">
    <Phone />
    <Mail />
    <Camera />
  </div>
</template>
<script setup lang="ts">
import Phone from "@/assets/img/phone.svg?component";
import Camera from "@/assets/img/camera.svg?component";
import Mail from "@/assets/img/mail.svg?component";
</script>
<style lang="scss">
.bottombar {
  width: 100%;
  height: 15vh;
  margin-top: -20px;
  display: flex;
  justify-content: space-evenly;
  align-items: center;

  & svg {
    padding: 12px;
    background-color: #eeeeee;
    
    border-radius: 20%;
    width: 30px;
    height: 30px;
  }
}
</style>