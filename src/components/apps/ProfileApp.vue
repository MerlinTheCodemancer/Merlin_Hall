<script setup lang="ts">
import paperLarge from '../../assets/paperPixelArtG.svg'

const baseUrl = import.meta.env.BASE_URL

const profile = {
  name: 'Merlin Codemancer',
  subtitle: 'Game Dev • Artist • Fullstack',
  avatarSrc: `${baseUrl}MyPortrait.png`,
  bannerSrc: `${baseUrl}magician.jpg`,
  bannerPosition: 'center 35%',
  about:
    'Olá! Sou Marcelo Ferreira, um desenvolvedor apaixonado por jogos, animação e cultura desde criança. CEO e fundador da Its High Play LTDA.',
} as const
</script>

<template>
  <div class="profile-app">
    <main class="profile-scroll" aria-label="Profile content">
      <section class="screen-content">
        <div class="page-banner">
          <div id="user-banner" class="user-banner croppable-image-advanced" aria-label="User banner">
            <div class="croppable-image-advanced-inner" data-image-frame="1">
              <img
                class="user-banner__image"
                :src="profile.bannerSrc"
                :alt="`${profile.name} banner`"
                :style="{ objectPosition: profile.bannerPosition }"
                loading="lazy"
              />
              <div class="croppable-image-advanced-spinner" data-image-spinner="1" style="display:none"></div>
            </div>
          </div>
        </div>
        <div class="hero">
          <div class="avatar">
            <img :src="profile.avatarSrc" :alt="profile.name" />
          </div>

          <div class="hero-text">
            <h1 class="name">{{ profile.name }}</h1>
            <p class="subtitle">{{ profile.subtitle }}</p>
          </div>
        </div>

        <div class="social-networks" :style="{ '--paper-url': `url(${paperLarge})` }">
          <h3>Minhas Redes Sociais</h3>
          <div class="social-grid social-tiles">
            <a
              class="social-tile"
              rel="noopener"
              target="_blank"
              href="https://discord.com/users/merlinthecodemancer"
              aria-label="Discord"
              title="Discord"
              style="--c1:#5865F2; --c2:#414cc7;"
            >
              <img class="social-svg" :src="`${baseUrl}icons/Discord.svg`" alt="Discord" loading="lazy" />
            </a>

            <a
              class="social-tile"
              rel="noopener"
              target="_blank"
              href="https://twitter.com/MerlinCodemanc1"
              aria-label="Twitter"
              title="Twitter"
              style="--c1:#1DA1F2; --c2:#0f1419;"
            >
              <img class="social-svg" :src="`${baseUrl}icons/x-twitter.svg`" alt="Twitter" loading="lazy" />
            </a>

            <a
              class="social-tile"
              rel="noopener"
              target="_blank"
              href="https://instagram.com/merlinthecodemancer"
              aria-label="Instagram"
              title="Instagram"
              style="--c1:#E4405F; --c2:#FCCC63;"
            >
              <img class="social-svg" :src="`${baseUrl}icons/instagram.svg`" alt="Instagram" loading="lazy" />
            </a>

            <a
              class="social-tile"
              rel="noopener"
              target="_blank"
              href="https://github.com/MerlinTheCodemancer"
              aria-label="GitHub"
              title="GitHub"
              style="--c1:#333333; --c2:#111111;"
            >
              <img class="social-svg" :src="`${baseUrl}icons/github.svg`" alt="GitHub" loading="lazy" />
            </a>

            <a
              class="social-tile"
              rel="noopener"
              target="_blank"
              href="https://reddit.com/u/MerlinTheCodemancer"
              aria-label="Reddit"
              title="Reddit"
              style="--c1:#ff4500; --c2:#c23100;"
            >
              <img class="social-svg" :src="`${baseUrl}icons/reddit.svg`" alt="Reddit" loading="lazy" />
            </a>

            <a
              class="social-tile"
              rel="noopener"
              target="_blank"
              href="https://www.linkedin.com/in/marcelo-deabreu-ferreira"
              aria-label="LinkedIn"
              title="LinkedIn"
              style="--c1:#0077B5; --c2:#005085;"
            >
              <img class="social-svg" :src="`${baseUrl}icons/linkedin.png`" alt="LinkedIn" loading="lazy" />
            </a>

            <a
              class="social-tile"
              rel="noopener"
              target="_blank"
              href="https://substack.com"
              aria-label="SUBSTACK"
              title="SUBSTACK"
              style="--c1:#9370DB; --c2:#6a4bb1;"
            >
              <img class="social-svg" :src="`${baseUrl}icons/Substack.svg`" alt="SUBSTACK" loading="lazy" />
            </a>

            <a
              class="social-tile"
              rel="noopener"
              target="_blank"
              href="https://www.artstation.com"
              aria-label="ARTSTATION"
              title="ARTSTATION"
              style="--c1:#13AFF0; --c2:#0b6f96;"
            >
              <img class="social-svg" :src="`${baseUrl}icons/artstation.svg`" alt="ARTSTATION" loading="lazy" />
            </a>

            <a
              class="social-tile"
              rel="noopener"
              target="_blank"
              href="https://www.newgrounds.com"
              aria-label="NEWGROUNDS"
              title="NEWGROUNDS"
              style="--c1:#EAA61E; --c2:#a86f00;"
            >
              <img class="social-svg" :src="`${baseUrl}icons/newgrounds.svg`" alt="NEWGROUNDS" loading="lazy" />
            </a>
          </div>
        </div>

        <div class="social-networkss social-networkss--about" :style="{ '--paper-url': `url(${paperLarge})` }">
          <h2>Sobre</h2>
          <p>{{ profile.about }}</p>
        </div>
      </section>
    </main>
  </div>
</template>

<style scoped>
.profile-app {
  height: 100%;
  width: 100%;
  overflow: hidden;
  display: flex;
  flex-direction: column;
}

.profile-scroll {
  flex: 1;
  overflow: hidden;
}

.screen-content {
  height: 100%;
  overflow-y: auto;
  padding: 18px;
  background: radial-gradient(circle at 30% 0%, rgba(255, 204, 0, 0.15), transparent 40%),
    linear-gradient(135deg, #1f1722 0%, #302836 60%, #1f1722 100%);
}

.page-banner {
  margin: -18px -18px 0 -18px;
  padding: 0;
}

.user-banner.croppable-image-advanced {
  position: relative;
  width: 100%;
  height: clamp(120px, 22vw, 170px);
  overflow: hidden;
  border-bottom: 8px solid rgba(0, 0, 0, 1);
  background: #ffffff;
}

.user-banner.croppable-image-advanced::after {
  content: '';
  position: absolute;
  inset: 0;
  background:
    linear-gradient(180deg, rgba(0, 0, 0, 0.18), rgba(0, 0, 0, 0.55)),
    radial-gradient(circle at 20% 10%, rgba(255, 255, 255, 0.14), transparent 45%);
  pointer-events: none;
}

.croppable-image-advanced-inner {
  position: relative;
  width: 100%;
  height: 100%;
}

.user-banner__image {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.hero {
  --avatar-overlap: 70px;
  display: grid;
  grid-template-columns: 84px 1fr;
  gap: 14px;
  align-items: center;
  margin-top: calc(var(--avatar-overlap) * -1);
  margin-bottom: 14px;
  position: relative;
  z-index: 1;
}

.avatar {
  width: 96px;
  height: 96px;
  border-radius: 100px;
  background: rgba(255, 94, 0, 0.5);
  border: 2px solid rgb(0, 0, 0);
  overflow: hidden;
}

.avatar img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.name {
  margin-left: 4px;
  font-size: 32px;
  color: #ffffff;
}

.subtitle {
  margin-left: 4px;
  font-size: 12px;
  color: rgba(255, 255, 255);
  text-shadow: #000000 6px 6px 10px;
}

/* CSS aplicado conforme solicitado */

.social-networks {
  background-image: var(--paper-url);
  background-position: center;
  background-repeat: no-repeat;
  background-size: contain;
  border-radius: 15px;
  padding: 30px;
  padding-bottom: 80px;
  margin-bottom: -50px;
  
}


.social-networks h3 {
  font-size: 34px;
  color: #ffffff;
  margin: 0 0 4px 0;
  font-weight: 700;
  text-align: center;
  text-shadow: #2c2c2c 2px 2px 4px;
}

.social-networks--about {
  padding: 70px;
  padding-left: 25px;
  padding-right: 25px;
  min-height: 60px;
}

.social-networkss {
  background-image: var(--paper-url);
  transform: scaleX(-1);
  background-position: center;
  background-repeat: no-repeat;
  background-size: contain;
  padding: 70px;
  padding-left: 25px;
  padding-right: 25px;
  padding-bottom: 80px;
  margin-bottom: -60px;
}

.social-networkss h2 {
  font-size: 40px;
  color: #ffffff;
  margin: 0px;
  font-weight: 700;
  text-align: center;
  transform: scaleX(-1);
  text-shadow: #2c2c2c 2px 2px 4px;
}

.social-networkss--about p {
  transform: scaleX(-1);
  margin-top: 0px;
  font-size: 12px;
  line-height: 1.5;
  color: #ffffff;
  text-shadow: #2c2c2c 4px 4px 6px;
  text-align: left;
  max-width: 70ch;

}

.social-grid {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  gap: 2px;
}

.social-tiles {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  gap: 2px;
}

.social-tile {
  position: relative;
  width: 100%;
  aspect-ratio: 1/1;
  display: grid;
  place-items: center;
  text-decoration: none;
  color: inherit;
  border-radius: 10px;
  overflow: hidden;
  background: #0f1114;
  border: 0;
  box-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
  transition: transform 0.32s cubic-bezier(0.2, 0.9, 0.3, 1), box-shadow 0.36s, filter 0.36s;
}

.social-tile::before {
  content: '';
  position: absolute;
  inset: 1px;
  border-radius: inherit;
  background: linear-gradient(
    120deg,
    color-mix(in srgb, var(--c1, #666) 28%, transparent),
    color-mix(in srgb, var(--c2, #333) 18%, transparent)
  );
  opacity: 0.45;
  pointer-events: none;
  transition: opacity 0.36s, filter 0.36s;
}

.social-tile::after {
  content: '';
  position: absolute;
  inset: -6px;
  border-radius: inherit;
  background: linear-gradient(120deg, var(--c1, #666), var(--c2, #333));
  opacity: 0;
  filter: blur(18px);
  transform: scale(0.8);
  transition: opacity 0.5s, transform 0.5s, filter 0.5s;
  mix-blend-mode: plus-lighter;
}

.social-svg {
  width: 58%;
  height: 58%;
  object-fit: contain;
  filter: drop-shadow(0 2px 4px rgba(0, 0, 0, 0.5));
  transition: transform 0.36s, opacity 0.36s;
}

.social-tile:hover,
.social-tile:focus-visible {
  transform: translateY(-8px) scale(1.08);
  box-shadow:
    0 18px 40px -20px color-mix(in srgb, var(--c1) 65%, transparent),
    0 0 0 1px color-mix(in srgb, var(--c1) 45%, #000);
}

.social-tile:hover::before,
.social-tile:focus-visible::before {
  opacity: 0.95;
  filter: brightness(1.18) saturate(1.18);
}

.social-tile:hover::after,
.social-tile:focus-visible::after {
  opacity: 0.9;
  transform: scale(1);
  filter: blur(26px);
}

.social-tile:active {
  transform: translateY(-3px) scale(0.98);
  transition: transform 0.12s;
}

.card {
  background: rgba(255, 255, 255, 0.92);
  border-radius: 14px;
  padding: 14px;
  margin-bottom: 12px;
  border: 2px solid rgba(0, 0, 0, 0.18);
}

.card h2 {
  margin: 0 0 8px;
  font-size: 14px;
  color: #1a1a1a;
}

.card p {
  margin: 0;
  font-size: 12px;
  line-height: 1.4;
  color: #2c2c2c;
}

.achievements {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 10px;
}

.achievement {
  background: rgba(31, 23, 34, 0.08);
  border: 1px solid rgba(0, 0, 0, 0.14);
  border-radius: 12px;
  padding: 10px;
  display: flex;
  gap: 10px;
  align-items: center;
}

.ach-icon {
  width: 34px;
  height: 34px;
  display: grid;
  place-items: center;
  border-radius: 10px;
  background: #ffffff;
  border: 1px solid rgba(0, 0, 0, 0.12);
}

.ach-label {
  display: block;
  font-size: 11px;
  color: #222;
}

.ach-value {
  display: block;
  font-size: 12px;
  color: #111;
}

@media (max-width: 480px) {
  .social-grid,
  .social-tiles {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>
