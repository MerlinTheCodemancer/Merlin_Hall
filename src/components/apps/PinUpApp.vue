<script setup lang="ts">
</script>

<template>
  <div class="pinup-app">
    <div class="pinup-header">
      <div class="pinup-icon">
        <span>🎭</span>
      </div>
      <h2>Pin-Up Gallery</h2>
    </div>
    
    <div class="gallery-content">
      <div class="gallery-item">
        <div class="gallery-image" style="background: linear-gradient(45deg, #FF69B4, #FFB6C1);">
          <span>👩‍🎨</span>
        </div>
        <h3>Vintage Style</h3>
      </div>
      
      <div class="gallery-item">
        <div class="gallery-image" style="background: linear-gradient(45deg, #DDA0DD, #DA70D6);">
          <span>💃</span>
        </div>
        <h3>Dance Series</h3>
      </div>
      
      <div class="gallery-item">
        <div class="gallery-image" style="background: linear-gradient(45deg, #F0E68C, #FFD700);">
          <span>🌟</span>
        </div>
        <h3>Golden Era</h3>
      </div>
    </div>
  </div>
</template>

<style scoped>
.pinup-app {
  padding: 20px;
  height: 100%;
  background: linear-gradient(135deg, #DDA0DD 0%, #DA70D6 100%);
  overflow-y: auto;
}

.pinup-header {
  text-align: center;
  margin-bottom: 25px;
}

.pinup-icon {
  width: 60px;
  height: 60px;
  background: rgba(255, 255, 255, 0.9);
  border-radius: 15px;
  margin: 0 auto 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  border: 3px solid #333;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

.pinup-icon span {
  font-size: 28px;
}

.pinup-header h2 {
  font-size: 22px;
  color: white;
  margin: 0;
  font-weight: bold;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
}

.gallery-content {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.gallery-item {
  background: rgba(255, 255, 255, 0.95);
  border-radius: 15px;
  padding: 20px;
  border: 3px solid #333;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  text-align: center;
}

.gallery-image {
  width: 80px;
  height: 80px;
  border-radius: 15px;
  margin: 0 auto 15px;
  display: flex;
  align-items: center;
  justify-content: center;
  border: 3px solid #333;
  font-size: 32px;
}

.gallery-item h3 {
  font-size: 18px;
  color: #333;
  margin: 0;
  font-weight: bold;
}
</style>