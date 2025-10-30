<script setup lang="ts">
import { ref } from 'vue'
import PhoneInterface from './components/PhoneInterface.vue'

const currentApp = ref<string | null>(null)

const openApp = (appName: string) => {
  currentApp.value = appName
}

const closeApp = () => {
  currentApp.value = null
}
</script>

<template>
  <div class="app-container">
    
    <PhoneInterface 
      :current-app="currentApp" 
      @open-app="openApp" 
      @close-app="closeApp" 
    />
  </div>
</template>

<style scoped>
.app-container {
  min-height: 100vh;
  /* Use animated fallbackgroun.gif as the primary background (place file in public/fallbackgroun.gif)
     Keep the existing repeating gradients and base gradient as fallbacks underneath. */
  /* primary animated background gif */
  background-image: url('/fallbackgroun.gif');
  background-position: center center;
  background-size: cover;
  background-repeat: no-repeat;

  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  overflow: hidden;
  padding: 20px;

}


@media (max-width: 768px) {
  .app-container {
    padding: 10px;
  }
  
}
</style>
