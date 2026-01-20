<script setup lang="ts">
import { computed, ref } from 'vue'
import paperLarge from '../../assets/paperPixelArtG.svg'
import crossboard from '../../assets/CrossboardPixelArt.svg'

type WorkItem = {
  id: string
  title: string
  price: string
  imageSrc?: string
  imageAlt?: string
  steamUrl: string
}

const baseUrl = import.meta.env.BASE_URL
const paperBack = new URL('../../assets/paperPixelArt-.svg', import.meta.url).href

const works = ref<WorkItem[]>([
  {
    id: 'game1',
    title: 'Fantasy Adventure RPG',
    price: 'R$ 29,99',
    imageSrc: `${baseUrl}itshigh.gif`,
    imageAlt: 'Fantasy Adventure Game',
    steamUrl: 'https://store.steampowered.com/app/example1',
  },
  {
    id: 'game2',
    title: 'Pixel Art Platformer',
    price: 'R$ 19,99',
    imageSrc: `${baseUrl}projects.gif`,
    imageAlt: 'Pixel Platformer Game',
    steamUrl: 'https://store.steampowered.com/app/example2',
  },
  {
    id: 'game3',
    title: 'Magic Academy Simulator',
    price: 'R$ 39,99',
    imageSrc: `${baseUrl}book.gif`,
    imageAlt: 'Magic Academy Game',
    steamUrl: 'https://store.steampowered.com/app/example3',
  },
])

const query = ref('')

const filteredWorks = computed(() => {
  const q = query.value.trim().toLowerCase()
  return works.value.filter((work) => {
    if (!q) return true
    const haystack = work.title.toLowerCase()
    return haystack.includes(q)
  })
})
</script>

<template>
  <div class="works-app">
    <div class="works-frame" :style="{ '--crossboard-url': `url(${crossboard})`, '--paper-url': `url(${paperLarge})`, '--paper-back-url': `url(${paperBack})` }">


      <section class="grid" aria-label="Lista de jogos">
        <a 
          v-for="work in filteredWorks" 
          :key="work.id" 
          class="card"
          :href="work.steamUrl"
          target="_blank"
          rel="noopener"
        >
          <div class="thumb" aria-hidden="true">
            <img v-if="work.imageSrc" class="thumb__img" :src="work.imageSrc" :alt="work.imageAlt || work.title" loading="lazy" />
            <div v-else class="thumb__placeholder">SEM IMAGEM</div>
          </div>

          <div class="content">
            <div class="title-price-container">
              <h3 class="title">{{ work.title }}</h3>
              <div class="price">{{ work.price }}</div>
            </div>
          </div>
        </a>

        <div v-if="filteredWorks.length === 0" class="empty">
          Nenhum jogo encontrado.
        </div>
      </section>
    </div>
  </div>
</template>


<style scoped>
.works-app {
  height: 100%;
  background: transparent;
  overflow: hidden;
}

.works-frame {
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

.works-header {
  display: grid;
  grid-template-columns: 70px 1fr;
  gap: 12px;
  align-items: center;
  margin-bottom: 14px;
}

.works-header__img {
  width: 70px;
  height: 70px;
  object-fit: contain;
}

.works-header__text h2 {
  margin: 0;
  color: #ffffff;
  font-size: 22px;
  text-shadow: #1a1a1a 3px 3px 5px;
}

.works-header__text p {
  margin: 2px 0 0 0;
  color: rgba(255, 255, 255, 0.9);
  font-size: 12px;
}

.controls {
  display: grid;
  gap: 10px;
  margin-bottom: 14px;
}

.search {
  width: 100%;
  border-radius: 12px;
  border: 3px solid #333;
  padding: 10px 12px;
  background: rgba(255, 255, 255, 0.95);
  font-size: 13px;
  outline: none;
}

.tags {
  display: flex;
  gap: 8px;
  flex-wrap: wrap;
}

.tag {
  border-radius: 999px;
  border: 2px solid #333;
  padding: 6px 10px;
  font-size: 11px;
  font-weight: 800;
  cursor: pointer;
  background: rgba(255, 255, 255, 0.92);
}

.tag.active {
  background: #4ECDC4;
  color: #111;
}

.grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 12px;
}

.card {
  border-radius: 14px;
  overflow: hidden;
  background-repeat: no-repeat;
  background-position: center;
  background-size: contain;
  text-decoration: none;
  color: inherit;

}

.thumb {
  margin-top: 10px;
  height: 250px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-image: var(--paper-url);
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
  padding-bottom: 50px;
  padding-top: 40px;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.thumb:hover {
  transform: translateY(-4px);
}

.thumb__img {
  width: 70%;
  height: 115%;
  object-fit: contain;
}

.thumb__placeholder {
  font-size: 11px;
  font-weight: 900;
  padding: 8px 10px;
  border-radius: 10px;

}

.content {
  height: 40%;
  margin-top: -15px;
  margin-bottom: 60px;
  padding-bottom: 20px;
  padding-top: 50px;
  padding-right: 25px;
  padding-left: 25px;
  background-image: var(--paper-back-url);
  background-repeat: no-repeat;
  background-position: center;
  background-size: contain;
  border: none;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.content:hover {
  transform: translateY(-4px);
}

.title-price-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 12px;
}

.title {
  margin: 0;
  font-size: 26px;
  color: #111;
  flex: 1;
}

.price {
  font-size: 16px;
  font-weight: 900;
  color: #ffffff;
  background: rgba(160, 45, 0, 0.9);
  padding-left: 4px;
  padding-right: 4px;
  padding-top: 8px;
  padding-bottom: 20px;
  border-radius: 8px;
  text-align: center;
  white-space: nowrap;
}

.empty {
  text-align: center;
  padding: 16px;
  border-radius: 12px;
  border: 3px dashed rgba(255, 255, 255, 0.8);
  color: rgba(255, 255, 255, 0.95);
  text-shadow: #1a1a1a 3px 3px 5px;
  background: rgba(0, 0, 0, 0.18);
}
</style>


