<template>
  <v-app>
    <div class="bgImage"/>
    <router-view class="main"/>
  </v-app>
</template>

<style>
  .bgImage {
    background-image: url("~@/assets/background.jpg");
    position: fixed;
    height: 100%;
    width: 100%;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    filter: blur(5px);
    transform: scale(1.1);
  }
</style>