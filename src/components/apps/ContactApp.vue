<script setup lang="ts">
</script>

<template>
  <div class="contact-app">
    <div class="contact-header">
      <img class="contact-image" src="/calendar.png" alt="contact" />
      <h2>Get in Touch</h2>
    </div>
    
    <div class="contact-content">
      <div class="contact-methods">
        <div class="contact-method">
          <div class="method-icon" style="background: #FF6B6B;">
            <span><img src="/Gmail.png" alt="Gmail" /></span>
          </div>
          <div class="method-info">
            <h3>Email</h3>
            <p>marcelo.doccs@gmail.com</p>
          </div>
        </div>
        
        <div class="contact-method">
          <div class="method-icon" style="background: #9B59B6;">
            <img src="/cake.png" alt="Cake" />
          </div>
          <div class="method-info">
            <h3>Idade</h3>
            <p>21 Anos</p>
          </div>
        </div>
      </div>
      
      <div class="social-networks">
        <h3>Minhas Redes Sociais</h3>
        <div class="social-grid social-tiles">
          <a class="social-tile" rel="noopener" target="_blank" href="https://discord.com/users/merlinthecodemancer" aria-label="Discord" title="Discord" style="--c1:#5865F2; --c2:#414cc7;">
            <img class="social-svg" src="/icons/Discord.svg" alt="Discord" loading="lazy" />

          </a>

          <a class="social-tile" rel="noopener" target="_blank" href="https://twitter.com/MerlinCodemanc1" aria-label="Twitter" title="Twitter" style="--c1:#1DA1F2; --c2:#0f1419;">
            <img class="social-svg" src="/icons/x-twitter.svg" alt="Twitter" loading="lazy" />

          </a>

          <a class="social-tile" rel="noopener" target="_blank" href="https://instagram.com/merlinthecodemancer" aria-label="Instagram" title="Instagram" style="--c1:#E4405F; --c2:#FCCC63;">
            <img class="social-svg" src="/icons/instagram.svg" alt="Instagram" loading="lazy" />

          </a>

          <a class="social-tile" rel="noopener" target="_blank" href="https://merlinthecodemancer.newgrounds.com" aria-label="Newgrounds" title="Newgrounds" style="--c1:#fbb040; --c2:#b3742a;">
            <img class="social-svg" src="/icons/newgrounds.svg" alt="Newgrounds" loading="lazy" />

          </a>

          <a class="social-tile" rel="noopener" target="_blank" href="https://github.com/MerlinTheCodemancer" aria-label="GitHub" title="GitHub" style="--c1:#333333; --c2:#111111;">
            <img class="social-svg" src="/icons/github.svg" alt="GitHub" loading="lazy" />

          </a>

          <a class="social-tile" rel="noopener" target="_blank" href="https://reddit.com/u/MerlinTheCodemancer" aria-label="Reddit" title="Reddit" style="--c1:#ff4500; --c2:#c23100;">
            <img class="social-svg" src="/icons/reddit.svg" alt="Reddit" loading="lazy" />

          </a>

          <a class="social-tile" rel="noopener" target="_blank" href="https://kick.com/merlinthecodemancer" aria-label="Kick" title="Kick" style="--c1:#53FC18; --c2:#2fae00;">
            <img class="social-svg" src="/icons/Kick.svg" alt="Kick" loading="lazy" />

          </a>

          <a class="social-tile" rel="noopener" target="_blank" href="https://www.linkedin.com/in/marcelo-deabreu-ferreira" aria-label="LinkedIn" title="LinkedIn" style="--c1:#0077B5; --c2:#005085;">
            <img class="social-svg" src="/icons/linkedin.png" alt="LinkedIn" loading="lazy" />

          </a>
        </div>
      </div>
      
  <div class="quick-contact">
        <h3>Entre em Contato</h3>
        <button class="email-button" onclick="window.location.href='mailto:marcelo.doccs@gmail.com?subject=Contato via Portfolio&body=Olá Marcelo, vi seu portfolio e gostaria de conversar sobre...'">
          <img class="email-icon" src="/Gmail.png" alt="Gmail" />
          <div class="email-info">
            <span class="email-title">Enviar Email</span>
            <span class="email-subtitle">marcelo.doccs@gmail.com</span>
          </div>
          <span class="send-arrow">→</span>
        </button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.contact-app {
  padding: 20px;
  height: 100%;
  background: transparent;
  overflow-y: auto;
  border: 3px solid #333;
  border-radius: 12px;
}

.contact-header {
  text-align: center;
  margin-bottom: 25px;
}

.contact-image {
  display: block;
  width: 96px;
  height: 96px;
  object-fit: contain;
  margin: 0 auto 8px;
}

.contact-header h2 {
  font-size: 22px;
  color: #333;
  margin: 0;
  font-weight: bold;
}

.contact-content {
  display: flex;
  flex-direction: column;
  gap: 25px;
}

.contact-methods {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.contact-method {
  background: transparent;
  border-radius: 12px;
  padding: 15px;
  border: 3px solid #333;
  box-shadow: none;
  display: flex;
  align-items: center;
  gap: 15px;
}

.method-icon {
  width: 50px;
  height: 50px;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  border: 3px solid #333;
  flex-shrink: 0;
}

.method-icon span {
  font-size: 20px;
}

/* Ensure icons fit inside the 50x50 .method-icon box */
.method-icon img {
  width: 100%;
  height: 100%;
  object-fit: contain;
  display: block;
}

.gmail-icon {
  width: 50px;
  height: 50px;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  border: 3px solid #333;
  flex-shrink: 0;
}

.gmail-icon span {
  font-size: 10px;
}

.gmail-icon img {
  width: 90%;
  height: 90%;
  object-fit: contain;
  display: block;
}

/* Email icon inside the quick-contact button */
.email-button img.email-icon {
  width: 44px;
  height: 44px;
  object-fit: contain;
  flex-shrink: 0;
}

.method-info h3 {
  font-size: 16px;
  color: #333;
  margin: 0 0 5px 0;
  font-weight: bold;
}

.method-info p {
  font-size: 14px;
  color: #555;
  margin: 0;
}

  .quick-contact {
  background: transparent;
  border-radius: 15px;
  padding: 18px;
  border: 3px solid #333;
  box-shadow: none;
}

.quick-contact h3 {
  font-size: 18px;
  color: #333;
  margin: 0 0 14px 0;
  font-weight: bold;
  text-align: center;
}

.email-button {
  width: 100%;
  background: linear-gradient(135deg, #4ECDC4, #45B7B8);
  color: white;
  border: 0;
  padding: 12px;
  border-radius: 12px;
  font-size: 15px;
  font-weight: 700;
  cursor: pointer;
  display: flex;
  align-items: center;
  gap: 12px;
  transition: transform .28s cubic-bezier(.2,.9,.3,1), box-shadow .36s;
  position:relative;
  overflow:hidden;
}

.email-button::before {
  content:'';
  position:absolute; inset:1px; border-radius:10px; z-index:0;
  background: linear-gradient(150deg, rgba(255,255,255,0.16), rgba(255,255,255,0.04));
  pointer-events:none;
}

.email-button .email-icon, .email-button .email-info, .email-button .send-arrow { position:relative; z-index:1; }

.email-button:hover { transform:translateY(-6px) scale(1.03); box-shadow: 0 12px 36px -16px rgba(78,205,196,.5), 0 0 0 1px rgba(78,205,196,.12); }

.email-icon { font-size: 22px; flex-shrink: 0; }

.email-info { flex:1; display:flex; flex-direction:column; text-align:left; }
.email-title { font-size:15px; font-weight:800; margin-bottom:2px; }
.email-subtitle { font-size:12px; opacity:.9; }
.send-arrow { font-size:18px; transition: transform .2s; }
.email-button:hover .send-arrow { transform:translateX(6px); }


.social-networks { background: transparent; border-radius:15px; padding:12px; border:3px solid #333; box-shadow:none; }
.social-networks h3 { font-size:18px; color:#333; margin:0 0 12px 0; font-weight:700; text-align:center; }
.social-grid { display:grid; grid-template-columns: repeat(4, 1fr); gap:10px; }
.social-tiles { display:grid; grid-template-columns: repeat(4, 1fr); gap:10px; }
.social-tile { position:relative; width:100%; aspect-ratio:1/1; display:grid; place-items:center; text-decoration:none; color:inherit; border-radius:12px; overflow:hidden; background:#0f1114; border:0; box-shadow:0 1px 2px rgba(0,0,0,.5); transition: transform .32s cubic-bezier(.2,.9,.3,1), box-shadow .36s, filter .36s; }
.social-tile::before { content:''; position:absolute; inset:1px; border-radius:inherit; background: linear-gradient(150deg, color-mix(in srgb,var(--c1, #666) 28%, transparent), color-mix(in srgb,var(--c2, #333) 18%, transparent)); opacity:.45; pointer-events:none; transition:opacity .36s, filter .36s; }
.social-tile::after { content:''; position:absolute; inset:-6px; border-radius:inherit; background:linear-gradient(120deg, var(--c1, #666), var(--c2, #333)); opacity:0; filter:blur(18px); transform:scale(.8); transition:opacity .5s, transform .5s, filter .5s; mix-blend-mode:plus-lighter; }
.social-svg { width:58%; height:58%; object-fit:contain; filter: drop-shadow(0 2px 4px rgba(0,0,0,.5)); transition: transform .36s, opacity .36s; }
.social-tile:hover, .social-tile:focus-visible { transform: translateY(-8px) scale(1.08); box-shadow:0 18px 40px -20px color-mix(in srgb,var(--c1) 65%, transparent), 0 0 0 1px color-mix(in srgb,var(--c1) 45%, #000); }
.social-tile:hover::before, .social-tile:focus-visible::before { opacity:.95; filter:brightness(1.18) saturate(1.18); }
.social-tile:hover::after, .social-tile:focus-visible::after { opacity:.9; transform:scale(1); filter:blur(26px); }
.social-tile:active { transform: translateY(-3px) scale(.98); transition: transform .12s; }

@media (max-width:480px) {
  .social-grid, .social-tiles { grid-template-columns: repeat(2, 1fr); }
}

@media (max-width: 480px) {
  .social-grid {
    grid-template-columns: 1fr;
  }
  
  .social-btn {
    font-size: 12px;
    padding: 10px;
  }
}
</style>