<script setup lang="ts">
</script>

<template>
  <div class="booklet-app">
    <div class="booklet-header">
      <div class="booklet-icon">
        <span>📖</span>
      </div>
      <h2>Art Booklet</h2>
    </div>
    
    <div class="booklet-content">
      <div class="booklet-page">
        <h3>Chapter 1: Digital Dreams</h3>
        <p>An exploration into the world of digital art and creative expression through modern web technologies.</p>
        <div class="page-art" style="background: linear-gradient(45deg, #FF6B6B, #4ECDC4);">
          <span>🎨</span>
        </div>
      </div>
      
      <div class="booklet-page">
        <h3>Chapter 2: Interactive Stories</h3>
        <p>Bringing stories to life through interactive web experiences and immersive user interfaces.</p>
        <div class="page-art" style="background: linear-gradient(45deg, #9B59B6, #3498DB);">
          <span>📱</span>
        </div>
      </div>
      
      <div class="booklet-page">
        <h3>Chapter 3: Future Visions</h3>
        <p>Looking ahead to the future of digital art and web design innovation.</p>
        <div class="page-art" style="background: linear-gradient(45deg, #F39C12, #E74C3C);">
          <span>🚀</span>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.booklet-app {
  padding: 20px;
  height: 100%;
  background: linear-gradient(135deg, #FF7F50 0%, #FF6347 100%);
  overflow-y: auto;
}

.booklet-header {
  text-align: center;
  margin-bottom: 25px;
}

.booklet-icon {
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

.booklet-icon span {
  font-size: 28px;
}

.booklet-header h2 {
  font-size: 22px;
  color: white;
  margin: 0;
  font-weight: bold;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
}

.booklet-content {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.booklet-page {
  background: rgba(255, 255, 255, 0.95);
  border-radius: 15px;
  padding: 20px;
  border: 3px solid #333;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.booklet-page h3 {
  font-size: 18px;
  color: #333;
  margin: 0 0 15px 0;
  font-weight: bold;
}

.booklet-page p {
  font-size: 14px;
  color: #555;
  margin: 0 0 15px 0;
  line-height: 1.5;
}

.page-art {
  width: 60px;
  height: 60px;
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  border: 3px solid #333;
  font-size: 24px;
  margin: 0 auto;
}
</style>