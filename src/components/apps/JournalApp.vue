<script setup lang="ts">
</script>

<template>
  <div class="journal-app">
    <div class="journal-header">
      <img class="journal-image" src="/itshigh.gif" alt="journal" />
      <h2>Creative Journal</h2>
    </div>
    
    <div class="journal-content">
      <div class="journal-entry">
        <div class="entry-date">Oct 16, 2024</div>
        <h3>New Portfolio Launch</h3>
        <p>Today I launched my new interactive portfolio with a creative phone interface. The design captures the playful spirit of mobile apps while showcasing my work professionally.</p>
      </div>
      
      <div class="journal-entry">
        <div class="entry-date">Oct 15, 2024</div>
        <h3>Animation Experiments</h3>
        <p>Working on some new character animation techniques. The blend between traditional 2D animation and modern web technologies is fascinating.</p>
      </div>
      
      <div class="journal-entry">
        <div class="entry-date">Oct 14, 2024</div>
        <h3>Color Theory Studies</h3>
        <p>Exploring vibrant color palettes inspired by pop art and street art. The yellow and pink combination is becoming a signature style.</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.journal-app {
  padding: 20px;
  height: 100%;
  background: transparent;
  overflow-y: auto;
  border: 3px solid #333;
  border-radius: 12px;
}

.journal-header {
  text-align: center;
  margin-bottom: 25px;
}

.journal-image {
  display: block;
  width: 96px;
  height: 96px;
  object-fit: contain;
  margin: 0 auto 8px;
}

.journal-header h2 {
  font-size: 22px;
  color: white;
  margin: 0;
  font-weight: bold;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
}

.journal-content {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.journal-entry {
  background: rgba(255, 255, 255, 0.95);
  border-radius: 15px;
  padding: 20px;
  border: 3px solid #333;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.entry-date {
  background: #4ECDC4;
  color: white;
  padding: 4px 10px;
  border-radius: 10px;
  font-size: 12px;
  font-weight: bold;
  border: 2px solid #333;
  display: inline-block;
  margin-bottom: 10px;
}

.journal-entry h3 {
  font-size: 18px;
  color: #333;
  margin: 0 0 15px 0;
  font-weight: bold;
}

.journal-entry p {
  font-size: 14px;
  color: #555;
  margin: 0;
  line-height: 1.5;
}
</style>