<script setup lang="ts">
import { computed, ref } from 'vue'
import paperLarge from '../../assets/paperPixelArtG.svg'
import crossboard from '../../assets/CrossboardPixelArt.svg'

type GalleryImage = {
  src: string
  alt?: string
  title?: string
  description?: string
}

type GalleryItem = {
  id: string
  title?: string
  images: GalleryImage[]
  category: string
  aspectRatio?: 'tall' | 'wide' | 'square'
  featured?: boolean
}

const baseUrl = import.meta.env.BASE_URL

const galleryItems = ref<GalleryItem[]>([
  {
    id: 'char-design',
    title: 'Character Design Collection',
    images: [
      { src: `${baseUrl}6350711.png`, alt: 'Dark Fantasy Character', title: 'Dark Fantasy Warrior', description: 'Personagem com armadura sombria e elementos fantásticos' },
      { src: `${baseUrl}magician.jpg`, alt: 'Magician Character', title: 'Arcane Magician', description: 'Mago com poderes arcanos e visual misterioso' },
      { src: `${baseUrl}b0b6566d41190467e2e0e22dbe5ee50a.jpg`, alt: 'Kawaii Character', title: 'Kawaii Style Character', description: 'Personagem fofo em estilo anime/kawaii' },
    ],
    category: 'Character Design',
    aspectRatio: 'tall',
    featured: true,
  },
  {
    id: 'ui-interfaces',
    title: 'UI/UX Design Portfolio',
    images: [
      { src: `${baseUrl}Screenshot 2025-10-16 175924.png`, alt: 'HOSAKA Terminal', title: 'Cyberpunk Terminal Interface', description: 'Interface futurista inspirada em cyberpunk' },
      { src: `${baseUrl}Screenshot 2025-10-16 180041.png`, alt: 'UI Design', title: 'Modern UI Components', description: 'Componentes de interface moderna e responsiva' },
    ],
    category: 'UI Design',
    aspectRatio: 'wide',
  },
  {
    id: 'digital-art',
    title: 'Digital Art & Portraits',
    images: [
      { src: `${baseUrl}MyPortrait.png`, alt: 'Digital Portrait', title: 'Self Portrait', description: 'Autorretrato digital com técnicas avançadas' },
      { src: `${baseUrl}library.jpg`, alt: 'Fantasy Environment', title: 'Mystical Library', description: 'Ambiente fantástico de biblioteca mística' },
    ],
    category: 'Digital Art',
    aspectRatio: 'square',
  },
  {
    id: 'branding-projects',
    title: 'Branding & Corporate',
    images: [
      { src: `${baseUrl}itshigh.gif`, alt: 'Its High Play Branding', title: 'Its High Play Studio', description: 'Identidade visual para estúdio de games' },
      { src: `${baseUrl}projects.gif`, alt: 'Project Showcase', title: 'Portfolio Projects', description: 'Showcase de projetos desenvolvidos' },
    ],
    category: 'Branding',
    aspectRatio: 'square',
  },
  {
    id: 'animations',
    title: 'Animation & Motion Graphics',
    images: [
      { src: `${baseUrl}origami.gif`, alt: 'Origami Animation', title: 'Paper Fold Animation', description: 'Animação de dobraduras em papel' },
      { src: `${baseUrl}work.gif`, alt: 'Work Animation', title: 'Professional Work Showcase', description: 'Animação mostrando trabalhos profissionais' },
      { src: `${baseUrl}book.gif`, alt: 'Book Animation', title: 'Interactive Book', description: 'Livro interativo com animações' },
    ],
    category: 'Animation',
    aspectRatio: 'tall',
  },
  {
    id: 'web-development',
    title: 'Web Development Projects',
    images: [
      { src: `${baseUrl}projects.gif`, alt: 'Web Projects', title: 'Portfolio Website', description: 'Site portfolio desenvolvido em Vue.js' },
      { src: `${baseUrl}Screenshot 2025-10-16 175924.png`, alt: 'Interface Design', title: 'Responsive Interfaces', description: 'Interfaces responsivas e modernas' },
    ],
    category: 'Web Dev',
    aspectRatio: 'wide',
  },
])

const selectedCategory = ref<string>('All')
const selectedItem = ref<GalleryItem | null>(null)
const currentImageIndex = ref<{ [key: string]: number }>({})

const categories = computed(() => {
  const cats = new Set(['All'])
  galleryItems.value.forEach(item => cats.add(item.category))
  return Array.from(cats)
})

const filteredItems = computed(() => {
  if (selectedCategory.value === 'All') {
    return galleryItems.value
  }
  return galleryItems.value.filter(item => item.category === selectedCategory.value)
})

const setCategory = (category: string) => {
  selectedCategory.value = category
}

const openItemDetail = (item: GalleryItem) => {
  selectedItem.value = item
}

const closeItemDetail = () => {
  selectedItem.value = null
}

const getCurrentImage = (item: GalleryItem): GalleryImage | undefined => {
  const index = currentImageIndex.value[item.id] || 0
  return item.images[index] || item.images[0]
}

const nextImage = (item: GalleryItem) => {
  const currentIndex = currentImageIndex.value[item.id] || 0
  const nextIndex = (currentIndex + 1) % item.images.length
  currentImageIndex.value[item.id] = nextIndex
}

const prevImage = (item: GalleryItem) => {
  const currentIndex = currentImageIndex.value[item.id] || 0
  const prevIndex = currentIndex === 0 ? item.images.length - 1 : currentIndex - 1
  currentImageIndex.value[item.id] = prevIndex
}
</script>

<template>
  <div class="gallery-app">
    <div class="gallery-frame" :style="{ '--crossboard-url': `url(${crossboard})` }">
      <!-- Masonry Gallery Grid -->
      <div v-if="!selectedItem" class="gallery-grid">
        <div
          v-for="item in filteredItems"
          :key="item.id"
          class="gallery-item"
          :class="[
            `aspect-${item.aspectRatio || 'square'}`,
            { featured: item.featured }
          ]"
          @click="openItemDetail(item)"
        >
          <div class="item-image-wrapper">
            <!-- Carousel Preview -->
            <div class="carousel-container">
              <img
                v-if="getCurrentImage(item)"
                class="item-image"
                :src="getCurrentImage(item)!.src"
                :alt="getCurrentImage(item)!.alt || item.title"
                loading="lazy"
              />
              
              <!-- Carousel Controls -->
              <div v-if="item.images.length > 1" class="carousel-controls">
                <button class="carousel-btn prev" @click.stop="prevImage(item)">‹</button>
                <button class="carousel-btn next" @click.stop="nextImage(item)">›</button>
              </div>
              
              <!-- Image Counter -->
              <div v-if="item.images.length > 1" class="image-counter">
                {{ (currentImageIndex[item.id] || 0) + 1 }}/{{ item.images.length }}
              </div>
            </div>
            
            <div class="item-overlay">
              <div class="item-info">
                <h3 v-if="item.title" class="item-title">{{ item.title }}</h3>
                <span class="item-category">{{ item.category }}</span>
                <div v-if="item.images.length > 1" class="image-count-badge">
                  {{ item.images.length }} imagens
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Detail View Modal -->
      <div v-else class="detail-view">
        <div class="detail-header">
          <button class="back-btn" @click="closeItemDetail">← Voltar</button>
          <h2 class="detail-title">{{ selectedItem.title }}</h2>
          <span class="detail-category">{{ selectedItem.category }}</span>
        </div>
        
        <div class="detail-content">
          <div 
            v-for="(image, index) in selectedItem.images" 
            :key="index"
            class="detail-image-item"
          >
            <div class="detail-image-wrapper">
              <img 
                :src="image.src" 
                :alt="image.alt || `Imagem ${index + 1}`"
                class="detail-image"
                loading="lazy"
              />
            </div>
            <div class="detail-image-info">
              <h4 v-if="image.title" class="detail-image-title">{{ image.title }}</h4>
              <p v-if="image.description" class="detail-image-description">{{ image.description }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.gallery-app {
  height: 100%;
  background: transparent;
  overflow: hidden;
}

.gallery-frame {
  height: 100%;
  overflow-y: auto;
  padding: 12px;
  background-image: var(--crossboard-url);
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}

.gallery-header {
  margin-bottom: 16px;
}

.header-content {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 12px;
  background: rgba(0, 0, 0, 0.8);
  border-radius: 12px;
  border: 2px solid #333;
}

.header-icon {
  width: 50px;
  height: 50px;
  object-fit: contain;
}

.header-text h2 {
  margin: 0;
  color: #ffffff;
  font-size: 20px;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.8);
}

.header-text p {
  margin: 2px 0 0 0;
  color: rgba(255, 255, 255, 0.8);
  font-size: 11px;
}

.category-filter {
  display: flex;
  gap: 6px;
  flex-wrap: wrap;
  margin-bottom: 16px;
  padding: 0 4px;
}

.category-btn {
  padding: 8px 12px;
  border-radius: 20px;
  border: 2px solid #333;
  background: rgba(255, 255, 255, 0.9);
  color: #333;
  font-size: 11px;
  font-weight: 800;
  cursor: pointer;
  transition: all 0.2s ease;
}

.category-btn:hover {
  background: rgba(255, 255, 255, 1);
  transform: translateY(-1px);
}

.category-btn.active {
  background: #4ECDC4;
  color: #111;
}

.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
  gap: 8px;
  grid-auto-rows: 120px;
}

.gallery-item {
  border-radius: 12px;
  overflow: hidden;
  border: 2px solid #333;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  cursor: pointer;
  position: relative;
}

.gallery-item:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 16px rgba(0, 0, 0, 0.4);
}

.gallery-item.aspect-tall {
  grid-row: span 2;
}

.gallery-item.aspect-wide {
  grid-column: span 2;
}

.gallery-item.aspect-square {
  grid-row: span 1;
}

.gallery-item.featured {
  grid-column: span 2;
  grid-row: span 2;
}

.item-image-wrapper {
  position: relative;
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.carousel-container {
  position: relative;
  width: 100%;
  height: 100%;
}

.item-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.gallery-item:hover .item-image {
  transform: scale(1.05);
}

.carousel-controls {
  position: absolute;
  top: 50%;
  left: 0;
  right: 0;
  transform: translateY(-50%);
  display: flex;
  justify-content: space-between;
  padding: 0 8px;
  opacity: 0;
  transition: opacity 0.2s ease;
}

.gallery-item:hover .carousel-controls {
  opacity: 1;
}

.carousel-btn {
  background: rgba(0, 0, 0, 0.7);
  border: none;
  color: white;
  width: 30px;
  height: 30px;
  border-radius: 50%;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 16px;
  font-weight: bold;
  transition: background 0.2s ease;
}

.carousel-btn:hover {
  background: rgba(0, 0, 0, 0.9);
}

.image-counter {
  position: absolute;
  top: 8px;
  right: 8px;
  background: rgba(0, 0, 0, 0.7);
  color: white;
  padding: 4px 8px;
  border-radius: 12px;
  font-size: 10px;
  font-weight: bold;
}

.item-overlay {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  background: linear-gradient(transparent, rgba(0, 0, 0, 0.8));
  padding: 12px 8px 8px;
  transform: translateY(100%);
  transition: transform 0.3s ease;
}

.gallery-item:hover .item-overlay {
  transform: translateY(0);
}

.item-info {
  color: white;
}

.item-title {
  margin: 0 0 4px 0;
  font-size: 12px;
  font-weight: 800;
  line-height: 1.2;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.8);
}

.item-category {
  font-size: 10px;
  background: rgba(78, 205, 196, 0.9);
  color: #111;
  padding: 2px 6px;
  border-radius: 10px;
  font-weight: 800;
}

.image-count-badge {
  margin-top: 4px;
  font-size: 9px;
  background: rgba(255, 255, 255, 0.2);
  padding: 2px 6px;
  border-radius: 8px;
  display: inline-block;
}

/* Detail View Styles */
.detail-view {
  height: 100%;
  display: flex;
  flex-direction: column;
}

.detail-header {
  display: flex;
  align-items: center;
  gap: 12px;
  padding: 12px;
  background: rgba(0, 0, 0, 0.8);
  border-radius: 12px;
  margin-bottom: 16px;
  border: 2px solid #333;
}

.back-btn {
  background: rgba(78, 205, 196, 0.9);
  border: none;
  color: #111;
  padding: 8px 12px;
  border-radius: 8px;
  cursor: pointer;
  font-weight: 800;
  font-size: 12px;
  transition: background 0.2s ease;
}

.back-btn:hover {
  background: rgba(78, 205, 196, 1);
}

.detail-title {
  margin: 0;
  color: white;
  font-size: 18px;
  flex: 1;
}

.detail-category {
  background: rgba(78, 205, 196, 0.9);
  color: #111;
  padding: 4px 8px;
  border-radius: 12px;
  font-size: 10px;
  font-weight: 800;
}

.detail-content {
  flex: 1;
  overflow-y: auto;
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.detail-image-item {
  background: rgba(255, 255, 255, 0.95);
  border-radius: 12px;
  border: 2px solid #333;
  overflow: hidden;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

.detail-image-wrapper {
  width: 100%;
  height: 200px;
  overflow: hidden;
}

.detail-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.detail-image-item:hover .detail-image {
  transform: scale(1.02);
}

.detail-image-info {
  padding: 12px;
}

.detail-image-title {
  margin: 0 0 6px 0;
  font-size: 14px;
  font-weight: 800;
  color: #111;
}

.detail-image-description {
  margin: 0;
  font-size: 12px;
  color: #555;
  line-height: 1.4;
}

/* Responsive adjustments */
@media (max-width: 400px) {
  .gallery-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 6px;
  }
  
  .gallery-item.aspect-wide,
  .gallery-item.featured {
    grid-column: span 1;
  }
  
  .category-filter {
    gap: 4px;
  }
  
  .category-btn {
    font-size: 10px;
    padding: 6px 10px;
  }
}

@media (min-width: 500px) {
  .gallery-grid {
    grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
  }
}
</style>
