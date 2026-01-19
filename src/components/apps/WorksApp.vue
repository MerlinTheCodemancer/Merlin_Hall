<script setup lang="ts">
import { computed, ref } from 'vue'
import paperLarge from '../../assets/paperPixelArtG.svg'
import crossboard from '../../assets/CrossboardPixelArt.svg'

type WorkLink = {
  label: string
  href: string
}

type WorkItem = {
  id: string
  title: string
  subtitle?: string
  description: string
  tags: string[]
  imageSrc?: string
  imageAlt?: string
  links?: WorkLink[]
}

const baseUrl = import.meta.env.BASE_URL

const works = ref<WorkItem[]>([
  {
    id: 'itshighplay',
    title: 'Its High Play LTDA',
    subtitle: 'Game Dev • Consultoria',
    description:
      'Projetos de jogos, protótipos e serviços digitais. Esta seção é estática — edite a lista para adicionar/remover trabalhos.',
    tags: ['GameDev', 'Studio'],
    imageSrc: `${baseUrl}itshigh.gif`,
    imageAlt: 'Its High Play',
    links: [
      { label: 'YouTube', href: 'https://www.youtube.com/@Merlin_Codemancer' },
      { label: 'GitHub', href: 'https://github.com/MerlinTheCodemancer' },
    ],
  },
  {
    id: 'portfolio',
    title: 'Merlin Hall (este site)',
    subtitle: 'Vue 3 + Vite',
    description:
      'Interface estilo “celular” para apresentar perfil, currículo, contato e trabalhos. Ideal pra abrir sem login.',
    tags: ['Web', 'Vue', 'Vite'],
    imageSrc: `${baseUrl}projects.gif`,
    imageAlt: 'Projects',
    links: [{ label: 'Repo', href: 'https://github.com/MerlinTheCodemancer/Merlin_Hall' }],
  },
  {
    id: 'art',
    title: 'Arte & Animação',
    subtitle: '2D/3D • Motion',
    description:
      'Coleção de estudos e peças para jogos/branding. Troque a imagem e os links pelos seus reais.',
    tags: ['Art', 'Animation'],
    imageSrc: `${baseUrl}book.gif`,
    imageAlt: 'Art',
    links: [
      { label: 'Instagram', href: 'https://www.instagram.com/merlin_codemancer/' },
      { label: 'ArtStation', href: 'https://www.artstation.com/merlinthecodemancer' },
    ],
  },
])

const query = ref('')
const activeTag = ref<string | null>(null)

const availableTags = computed(() => {
  const set = new Set<string>()
  for (const work of works.value) {
    for (const tag of work.tags) {
      set.add(tag)
    }
  }
  return Array.from(set).sort((a, b) => a.localeCompare(b))
})

const filteredWorks = computed(() => {
  const q = query.value.trim().toLowerCase()
  return works.value.filter((work) => {
    const matchesTag = !activeTag.value || work.tags.includes(activeTag.value)
    if (!matchesTag) return false
    if (!q) return true
    const haystack = [work.title, work.subtitle ?? '', work.description, work.tags.join(' ')].join(' ').toLowerCase()
    return haystack.includes(q)
  })
})

function setTag(tag: string | null) {
  activeTag.value = tag
}
</script>

<template>
  <div class="works-app">
    <div class="works-frame" :style="{ '--crossboard-url': `url(${crossboard})`, '--paper-url': `url(${paperLarge})` }">


      <section class="grid" aria-label="Lista de trabalhos">
        <article v-for="work in filteredWorks" :key="work.id" class="card">
          <div class="thumb" aria-hidden="true">
            <img v-if="work.imageSrc" class="thumb__img" :src="work.imageSrc" :alt="work.imageAlt || work.title" loading="lazy" />
            <div v-else class="thumb__placeholder">SEM IMAGEM</div>
          </div>

          <div class="content">
            <h3 class="title">{{ work.title }}</h3>
            <p v-if="work.subtitle" class="subtitle">{{ work.subtitle }}</p>
            <p class="desc">{{ work.description }}</p>

            <div class="chips" aria-label="Tags">
              <span v-for="tag in work.tags" :key="tag" class="chip">{{ tag }}</span>
            </div>

            <div v-if="work.links?.length" class="links" aria-label="Links">
              <a v-for="lnk in work.links" :key="lnk.href" class="link" :href="lnk.href" target="_blank" rel="noopener">
                {{ lnk.label }}
              </a>
            </div>
          </div>
        </article>

        <div v-if="filteredWorks.length === 0" class="empty">
          Nenhum resultado.
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
  border: 3px solid #333;
  overflow: hidden;
  background-image: var(--paper-url);
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.18);
}

.thumb {
  height: 140px;
  background: rgba(0, 0, 0, 0.15);
  border-bottom: 3px solid rgba(0, 0, 0, 0.35);
  display: flex;
  align-items: center;
  justify-content: center;
}

.thumb__img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.thumb__placeholder {
  font-size: 11px;
  font-weight: 900;
  background: rgba(255, 255, 255, 0.9);
  padding: 8px 10px;
  border-radius: 10px;
  border: 2px solid #333;
}

.content {
  padding: 12px 12px 14px;
}

.title {
  margin: 0;
  font-size: 16px;
  color: #111;
}

.subtitle {
  margin: 3px 0 0 0;
  font-size: 12px;
  color: rgba(0, 0, 0, 0.7);
  font-weight: 800;
}

.desc {
  margin: 8px 0 0 0;
  font-size: 12px;
  color: rgba(0, 0, 0, 0.85);
  line-height: 1.45;
}

.chips {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
  margin-top: 10px;
}

.chip {
  background: rgba(78, 205, 196, 0.95);
  color: #111;
  padding: 5px 10px;
  border-radius: 999px;
  font-size: 11px;
  font-weight: 900;
  border: 2px solid #333;
}

.links {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin-top: 10px;
}

.link {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 7px 10px;
  border-radius: 10px;
  border: 2px solid #333;
  background: rgba(255, 255, 255, 0.9);
  color: #111;
  font-weight: 900;
  font-size: 11px;
  text-decoration: none;
}

.link:hover {
  filter: brightness(1.05);
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


