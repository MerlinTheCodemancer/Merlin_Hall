<script setup lang="ts">
</script>

<template>
  <div class="shop-app">
    <div class="shop-header">
      <img class="shop-image" src="/6350711.png" alt="shop" />
      <h2>Art Shop</h2>
    </div>
    
    <div class="shop-content">
      <div class="product-grid">
        <div class="product-item">
          <img class="product-image" src="/6350711.png" alt="product" />
          <h3>Digital Art Prints</h3>
          <p>High-quality digital art prints</p>
          <span class="price">$25.00</span>
        </div>
        
        <div class="product-item">
          <img class="product-image" src="/6350711.png" alt="product" />
          <h3>Custom Illustrations</h3>
          <p>Personalized character designs</p>
          <span class="price">$150.00</span>
        </div>
        
        <div class="product-item">
          <img class="product-image" src="/6350711.png" alt="product" />
          <h3>Web Design Templates</h3>
          <p>Creative web design packages</p>
          <span class="price">$89.00</span>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.shop-app {
  padding: 20px;
  height: 100%;
  background: transparent;
  overflow-y: auto;
  border: 3px solid #333;
  border-radius: 12px;
}

.shop-header {
  text-align: center;
  margin-bottom: 25px;
}

.shop-image {
  display: block;
  width: 96px;
  height: 96px;
  object-fit: contain;
  margin: 0 auto 8px;
}

.shop-header h2 {
  font-size: 22px;
  color: white;
  margin: 0;
  font-weight: bold;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
}

.product-grid {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.product-item {
  background: transparent;
  border-radius: 15px;
  padding: 15px;
  border: 3px solid #333;
  box-shadow: none;
  text-align: center;
}

.product-image {
  display: block;
  width: 96px;
  height: 96px;
  object-fit: contain;
  margin: 0 auto 12px;
}

.product-item h3 {
  font-size: 16px;
  color: #333;
  margin: 0 0 8px 0;
  font-weight: bold;
}

.product-item p {
  font-size: 13px;
  color: #555;
  margin: 0 0 10px 0;
}

.price {
  background: #4ECDC4;
  color: white;
  padding: 6px 12px;
  border-radius: 12px;
  font-size: 14px;
  font-weight: bold;
  border: 2px solid #333;
}
</style>