<template>
  <v-app>
    <v-app-bar :style="{ backgroundColor: navColor }">
      <v-container class="d-flex align-center">
        <v-app-bar-title lang="en">
          <v-icon class="mr-2">mdi-timer</v-icon> Pomodoro
        </v-app-bar-title>
        <v-btn prepend-icon="mdi-weather-sunny" to="/">首頁</v-btn>
        <v-btn prepend-icon="mdi-weather-cloudy" to="/list">事項</v-btn>
        <v-btn prepend-icon="mdi-weather-pouring" to="/settings">設定</v-btn>
      </v-container>
    </v-app-bar>

    <!-- 設定背景圖片 -->
    <v-main class="background">
      <router-view v-slot="{ Component }">
        <keep-alive include="index">
          <component :is="Component"></component>
        </keep-alive>
      </router-view>
    </v-main>
  </v-app>
</template>

<script setup>
import { ref } from 'vue';

// 設定導航欄顏色
const navColor = ref('#9D9285'); // 預設顏色
</script>


<style>

/* 背景圖片設定 */
.background {
  background-image: url('./assets/BG.jpg'); /* 替換成你的圖片網址 */
  background-size: cover;
  background-position: center;
  background-attachment: fixed; /* 讓背景固定不變 */
}
</style>
