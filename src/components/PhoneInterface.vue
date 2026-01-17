<script setup lang="ts">
import { ref, computed } from 'vue'

// App components imports
import ProfileApp from './apps/ProfileApp.vue'
import InfoApp from './apps/InfoApp.vue'
import WorksApp from './apps/WorksApp.vue'
import ContactApp from './apps/ContactApp.vue'
import ShopApp from './apps/ShopApp.vue'

interface Props {
  currentApp: string | null
}

interface Emits {
  (e: 'open-app', appName: string): void
  (e: 'close-app'): void
}

const props = defineProps<Props>()
const emit = defineEmits<Emits>()

const baseUrl = import.meta.env.BASE_URL

const currentTime = ref(new Date().toLocaleTimeString('pt-BR', { 
  hour: '2-digit', 
  minute: '2-digit' 
}))

// Update time every minute
setInterval(() => {
  currentTime.value = new Date().toLocaleTimeString('pt-BR', { 
    hour: '2-digit', 
    minute: '2-digit' 
  })
}, 60000)

const apps = [
  { name: 'profile', label: 'PROFILE', icon: 'perfil', color: '#FFD700' },
  { name: 'info', label: 'INFO', icon: 'Book', color: '#87CEEB' },
  { name: 'works', label: 'WORKS', icon: 'compass', color: '#FF6347' },
  { name: 'contact', label: 'CONTACT', icon: 'arroba', color: '#90EE90' },
  { name: 'shop', label: 'SHOP', icon: 'Shop', color: '#2F4F2F' },
  { name: 'youtube', label: 'YOUTUBE', icon: 'youtube', color: '#FF0000' },
  { name: 'substack', label: 'SUBSTACK', icon: 'Substack', color: '#9370DB' },
  { name: 'github', label: 'GITHUB', icon: 'github', color: '#1a1a1a' },
  { name: 'artstation', label: 'ARTSTATION', icon: 'artstation', color: '#13AFF0' },
  { name: 'newgrounds', label: 'NEWGROUNDS', icon: 'newgrounds', color: '#EAA61E' },
  { name: 'instagram', label: 'INSTAGRAM', icon: 'instagram', color: '#E4405F' },
  { name: 'kick', label: 'KICK', icon: 'Kick', color: '#5AF60D' }
]

// mapping for inline SVG icons used on the home app grid
const getIcon = (name: string) => {
  const svgs: Record<string, string> = {
    profile: `
      <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
        <circle cx="12" cy="8" r="3.2" fill="white" />
        <path d="M4 20c0-3.3 3.6-6 8-6s8 2.7 8 6" fill="white" />
      </svg>
    `,

    info: `
      <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
        <path d="M1 12s4-7 11-7 11 7 11 7-4 7-11 7S1 12 1 12z" fill="white" />
        <circle cx="12" cy="12" r="2.2" fill="#333" />
      </svg>
    `,

    works: `
      <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
        <path d="M12 2l2.6 6.6L21 9l-5 3.7L17.2 21 12 17.8 6.8 21 8 12.7 3 9l6.4-0.4L12 2z" fill="white" />
      </svg>
    `,

    contact: `
      <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
        <rect x="2" y="5" width="20" height="14" rx="2" fill="white" />
        <path d="M3 7l9 6 9-6" fill="#e6e6e6" />
      </svg>
    `,

    animation: `
      <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
        <rect x="3" y="6" width="18" height="12" rx="1.5" fill="white" />
        <path d="M3 6l4-3 4 3 4-3 4 3" stroke="#e6e6e6" stroke-width="0.5" fill="none" />
      </svg>
    `
  }

  return svgs[name] || ''
}


const currentAppComponent = computed(() => {
  const componentMap: Record<string, any> = {
    profile: ProfileApp,
    info: InfoApp,
    works: WorksApp,
    contact: ContactApp,
    shop: ShopApp,

  }
  return props.currentApp ? componentMap[props.currentApp] : null
})

const openApp = (appName: string) => {
  if (appName === 'substack') {
    window.open('https://merlinthecodemancer.substack.com', '_blank')
    return
  }
  if (appName === 'youtube') {
    window.open('https://www.youtube.com/@Merlin_Codemancer', '_blank')
    return
  }
  if (appName === 'github') {
    window.open('https://github.com/merlinthecodemancer', '_blank')
    return
  }
  if (appName === 'artstation') {
    window.open('https://www.artstation.com/merlinthecodemancer', '_blank')
    return
  }
  if (appName === 'newgrounds') {
    window.open('https://merlinthecodemancer.newgrounds.com', '_blank')
    return
  }
  if (appName === 'instagram') {
    window.open('https://www.instagram.com/merlin_codemancer/', '_blank')
    return
  }
  if (appName === 'kick') {
    window.open('https://kick.com/merlin_codemancer', '_blank')
    return
  }
  emit('open-app', appName)
}

const closeApp = () => {
  emit('close-app')
}
</script>

<template>
  <div class="phone-container">
    <!-- Phone Frame -->
    <div class="phone-frame">
      <!-- Status Bar -->
      <div class="status-bar">
        <div class="notch"></div>
        <div class="status-left">
          <span class="time">{{ currentTime }}</span>
        </div>
        <div class="status-right">
          <span class="signal">●●●</span>
          <span class="wifi">📶</span>
          <span class="battery">🔋</span>
        </div>
      </div>

      <!-- Screen Content -->
      <div class="screen-content">
        <!-- Home Screen -->
        <div v-if="!currentApp" class="home-screen">
          <!-- Character illustration area -->
        

          <!-- App Grid -->
          <div class="app-grid">
            <div 
              v-for="app in apps" 
              :key="app.name"
              class="app-icon"
              :style="{ backgroundColor: app.color }"
              @click="openApp(app.name)"
            >
              <template v-if="app.icon">
                <img class="app-img" :src="`${baseUrl}icons/${app.icon}.svg`" :alt="app.label" />
              </template>
              <template v-else>
                <span class="app-svg" v-html="getIcon(app.name)"></span>
              </template>
              <span class="app-label">{{ app.label }}</span>
            </div>
          </div>

          <!-- Bottom Text -->
          <div class="bottom-text">
            <h1>Merlin Codemancer</h1>
            <h2>Portfolio</h2>
          </div>
        </div>

        <!-- App Screen -->
        <div v-else class="app-screen">
          <div class="app-header">
            <button class="back-button" @click="closeApp">←</button>
            <span class="app-title">{{ apps.find(a => a.name === currentApp)?.label }}</span>
            <div class="app-actions"></div>
          </div>
          
          <div class="app-content">
            <component :is="currentAppComponent" v-if="currentAppComponent" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.phone-container {
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1;
  position: relative;
}

.phone-frame {
  width: 420px;
  height: 820px;
  background: linear-gradient(145deg, #1C1C1E, #2C2C2E);
  border-radius: 44px;
  padding: 16px;
  border: 2px solid #3A3A3C;
  box-shadow: 
    0 0 0 1px #000,
    0 0 50px rgba(0, 0, 0, 0.6),
    inset 0 1px 0 rgba(255, 255, 255, 0.1);
  position: relative;
  overflow: hidden;
}

.status-bar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: white;
  font-size: 14px;
  font-weight: 600;
  margin-bottom: 8px;
  padding: 8px 5px 0;
  position: relative;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
}

.notch {
  position: absolute;
  top: -12px;
  left: 50%;
  transform: translateX(-50%);
  width: 120px;
  height: 24px;
  background: #000;
  border-radius: 0 0 16px 16px;
  z-index: 10;
}

.status-left {
  flex: 1;
  text-align: left;
}

.status-right {
  flex: 1;
  text-align: right;
  display: flex;
  justify-content: flex-end;
  gap: 4px;
}

.time {
  font-size: 16px;
  font-weight: 600;
}

.signal, .wifi, .battery {
  font-size: 12px;
  opacity: 0.9;
}

.screen-content {
  width: 100%;
  height: calc(100% - 34px);
  background: 
    /* Foreground: animated fallback gif */
    url('/library.jpg') center center / cover no-repeat,
    /* Library shelf pattern fallback */
     linear-gradient(135deg, #2B1810 0%, #1A0F0A 100%);
  border-radius: 34px;
  position: relative;
  overflow: hidden;
  image-rendering: pixelated;
  border: 1px solid rgba(255, 255, 255, 0.1);
  box-shadow: 
    inset 0 2px 6px rgba(0, 0, 0, 0.35),
    0 1px 0 rgba(255, 255, 255, 0.05);
}

.home-screen {
  height: 100%;
  display: flex;
  flex-direction: column;
  padding: 40px 20px 20px;
  background: rgba(0, 0, 0, 0.2);
  border-radius: 28px;
}

.app-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 15px;
  margin-bottom: 30px;
  padding: 0 10px;
}

.app-icon {
  aspect-ratio: 1;
  border-radius: 22%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: all 0.2s ease;
  border: 1px solid rgba(0, 0, 0, 0.2);
  position: relative;
  overflow: hidden;
}

.app-icon::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 50%;
  background: linear-gradient(180deg, 
    rgba(255, 255, 255, 0.7) 0%,
    rgba(255, 255, 255, 0.3) 50%,
    rgba(255, 255, 255, 0.1) 100%);
  border-radius: inherit;
  pointer-events: none;
}

.app-icon:hover {
  transform: scale(1.05);
  box-shadow: 
    0 4px 20px rgba(0, 0, 0, 0.4),
    inset 0 1px 0 rgba(255, 255, 255, 0.7),
    inset 0 0 30px rgba(255, 255, 255, 0.3);
}

.app-icon:active {
  transform: scale(0.95);
  box-shadow: 
    0 1px 5px rgba(0, 0, 0, 0.2),
    inset 0 1px 0 rgba(255, 255, 255, 0.5),
    inset 0 0 15px rgba(0, 0, 0, 0.1);
}

.app-emoji {
  font-size: 36px;
  margin-bottom: 4px;
  filter: drop-shadow(0 2px 4px rgba(0, 0, 0, 0.4));
  position: relative;
  z-index: 2;
}

.app-svg svg {
  width: 36px;
  height: 36px;
  display: block;
  margin-bottom: 6px;
  filter: drop-shadow(0 2px 6px rgba(0,0,0,0.4));
}

.app-img {
  width: 48px;
  height: 48px;
  object-fit: contain;
  margin-bottom: 6px;
  filter: drop-shadow(0 2px 6px rgba(0,0,0,0.4));
}

.app-label {
  font-size: 10px;
  font-weight: 600;
  color: white;
  text-align: center;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.8);
  letter-spacing: 0.2px;
  position: relative;
  z-index: 2;
}

.bottom-text {
  text-align: center;
  margin-top: auto;
}

.bottom-text h1 {
  font-size: 24px;
  font-weight: bold;
  color: #F5DEB3;
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.7);
}

.bottom-text h2 {
  font-size: 18px;
  font-weight: bold;
  color: #F5DEB3;
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.7);
}

.app-screen {
  height: 100%;
  display: flex;
  flex-direction: column;
}

.app-header {
  display: flex;
  align-items: center;
  padding: 15px 20px;
  background: rgba(255, 255, 255, 0.9);
  border-bottom: 2px solid #333;
}

.back-button {
  background: none;
  border: none;
  font-size: 20px;
  cursor: pointer;
  padding: 5px;
  border-radius: 50%;
  width: 35px;
  height: 35px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.back-button:hover {
  background: rgba(0, 0, 0, 0.1);
}

.app-title {
  flex: 1;
  text-align: center;
  font-weight: bold;
  font-size: 16px;
  color: #333;
}

.app-content {
  flex: 1;
  overflow-y: auto;
}

/* Mobile Responsive */
@media (max-width: 1024px) {
  .phone-frame {
    width: 75vw;
    max-width: 420px;
    height: 90vh;
    max-height: 820px;
  }
  
  .app-grid {
    gap: 12px;
  }
  
  .app-emoji {
    font-size: 20px;
  }
  
  .app-label {
    font-size: 9px;
  }
}

@media (max-width: 480px) {
  .phone-frame {
    width: 95vw;
    height: 85vh;
    border-radius: 20px;
    padding: 12px 10px;
  }
  
  .screen-content {
    border-radius: 15px;
  }
  
  .home-screen {
    padding: 15px;
  }
}
</style>
