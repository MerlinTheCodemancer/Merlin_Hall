<script setup lang="ts">
import crossboard from '../../assets/CrossboardPixelArt.svg'
import paperLarge from '../../assets/paperPixelArtG.svg'

const baseUrl = import.meta.env.BASE_URL
</script>

<template>
  <div class="shop-app">
    <div class="shop-frame" :style="{ '--crossboard-url': `url(${crossboard})`, '--paper-url': `url(${paperLarge})` }">
      <header class="shop-header">
        <img class="shop-header__img" :src="`${baseUrl}cake.png`" alt="Shop" loading="lazy" />
        <div class="shop-header__text">
          <h2>Shop</h2>
          <p>Em breve</p>
        </div>
      </header>

      <section class="card" aria-label="Shop em breve">
        <h3>Loja em construção</h3>
        <p>
          Aqui você pode colocar links de Gumroad / Itch.io / Steam / produtos digitais.
          Por enquanto, é só um placeholder para manter o app funcionando.
        </p>
        <a class="btn" href="https://linktr.ee/" target="_blank" rel="noopener">Adicionar links</a>
      </section>
    </div>
  </div>
</template>

<style scoped>
.shop-app {
  height: 100%;
  background: transparent;
  overflow: hidden;
}

.shop-frame {
  height: 100%;
  overflow-y: auto;
  padding: 16px;
  border: 3px solid #333;
  border-radius: 12px;
  background-image: var(--crossboard-url);
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}

.shop-header {
  display: grid;
  grid-template-columns: 70px 1fr;
  gap: 12px;
  align-items: center;
  margin-bottom: 14px;
}

.shop-header__img {
  width: 70px;
  height: 70px;
  object-fit: contain;
}

.shop-header__text h2 {
  margin: 0;
  color: #ffffff;
  font-size: 22px;
  text-shadow: #1a1a1a 3px 3px 5px;
}

.shop-header__text p {
  margin: 2px 0 0 0;
  color: rgba(255, 255, 255, 0.9);
  font-size: 12px;
}

.card {
  border-radius: 14px;
  border: 3px solid #333;
  padding: 14px;
  background-image: var(--paper-url);
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}

.card h3 {
  margin: 0;
  font-size: 18px;
  color: #111;
}

.card p {
  margin: 10px 0 0 0;
  font-size: 13px;
  line-height: 1.45;
  color: rgba(0, 0, 0, 0.85);
}

.btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  margin-top: 12px;
  padding: 10px 12px;
  border-radius: 12px;
  border: 3px solid #333;
  background: rgba(78, 205, 196, 0.95);
  color: #111;
  text-decoration: none;
  font-weight: 900;
  font-size: 12px;
}

.btn:hover {
  filter: brightness(1.05);
}
</style>
