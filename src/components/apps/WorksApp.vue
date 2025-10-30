<script setup lang="ts">
</script>

<template>
  <div class="works-app">
      <div class="works-header">
        <img class="works-image" src="/work.gif" alt="works" />
        <h2>My Works</h2>
      </div>
    
    <div class="achievements-gallery">
      <div class="gallery-header">
        <div class="stats">
          <span class="achievement-counter">🏆 12/15 Conquistas Desbloqueadas</span>
          <span class="xp-counter">⭐ 2,350 XP Total</span>
        </div>
      </div>
      
      <div class="achievements-grid">
        <!-- Linha 1 -->
        <div class="achievement-slot unlocked" data-rarity="legendary">
          <div class="achievement-icon ceo-icon">👑</div>
          <div class="achievement-info">
            <h4>CEO Fundador</h4>
            <p>Fundou sua própria empresa de jogos</p>
            <span class="achievement-xp">+500 XP</span>
            <span class="rarity legendary">Lendário</span>
          </div>
        </div>
        
        <div class="achievement-slot unlocked" data-rarity="epic">
          <div class="achievement-icon fullstack-icon">💻</div>
          <div class="achievement-info">
            <h4>FullStack Master</h4>
            <p>Dominou desenvolvimento completo</p>
            <span class="achievement-xp">+300 XP</span>
            <span class="rarity epic">Épico</span>
          </div>
        </div>
        
        <div class="achievement-slot unlocked" data-rarity="rare">
          <div class="achievement-icon international-icon">🌍</div>
          <div class="achievement-info">
            <h4>Cidadão Global</h4>
            <p>Viveu com europeus por 3 meses</p>
            <span class="achievement-xp">+200 XP</span>
            <span class="rarity rare">Raro</span>
          </div>
        </div>
        
        <!-- Linha 2 -->
        <div class="achievement-slot unlocked" data-rarity="epic">
          <div class="achievement-icon gamedev-icon">🎮</div>
          <div class="achievement-info">
            <h4>Game Developer</h4>
            <p>Especialista em Unreal Engine 5</p>
            <span class="achievement-xp">+350 XP</span>
            <span class="rarity epic">Épico</span>
          </div>
        </div>
        
        <div class="achievement-slot unlocked" data-rarity="rare">
          <div class="achievement-icon database-icon">🗄️</div>
          <div class="achievement-info">
            <h4>Database Wizard</h4>
            <p>Consultor em análise de BD</p>
            <span class="achievement-xp">+250 XP</span>
            <span class="rarity rare">Raro</span>
          </div>
        </div>
        
        <div class="achievement-slot unlocked" data-rarity="uncommon">
          <div class="achievement-icon chef-icon">🍔</div>
          <div class="achievement-info">
            <h4>MasterChef Junior</h4>
            <p>Melhor hambúrguer da escola</p>
            <span class="achievement-xp">+100 XP</span>
            <span class="rarity uncommon">Incomum</span>
          </div>
        </div>
        
        <!-- Linha 3 -->
        <div class="achievement-slot unlocked" data-rarity="rare">
          <div class="achievement-icon artist-icon">🎨</div>
          <div class="achievement-info">
            <h4>Digital Artist</h4>
            <p>Mestre em Photoshop e Blender</p>
            <span class="achievement-xp">+200 XP</span>
            <span class="rarity rare">Raro</span>
          </div>
        </div>
        
        <div class="achievement-slot unlocked" data-rarity="uncommon">
          <div class="achievement-icon multilingual-icon">🗣️</div>
          <div class="achievement-info">
            <h4>Poliglota</h4>
            <p>Inglês fluente conquistado</p>
            <span class="achievement-xp">+150 XP</span>
            <span class="rarity uncommon">Incomum</span>
          </div>
        </div>
        
        <div class="achievement-slot unlocked" data-rarity="rare">
          <div class="achievement-icon student-icon">🎓</div>
          <div class="achievement-info">
            <h4>Eterno Estudante</h4>
            <p>Múltiplas formações completadas</p>
            <span class="achievement-xp">+180 XP</span>
            <span class="rarity rare">Raro</span>
          </div>
        </div>
        
        <!-- Linha 4 -->
        <div class="achievement-slot unlocked" data-rarity="uncommon">
          <div class="achievement-icon logistics-icon">📦</div>
          <div class="achievement-info">
            <h4>Mestre da Logística</h4>
            <p>Organizou expedições na Magalu</p>
            <span class="achievement-xp">+120 XP</span>
            <span class="rarity uncommon">Incomum</span>
          </div>
        </div>
        
        <div class="achievement-slot unlocked" data-rarity="common">
          <div class="achievement-icon service-icon">☕</div>
          <div class="achievement-info">
            <h4>Bartender Pro</h4>
            <p>Atendimento de qualidade</p>
            <span class="achievement-xp">+80 XP</span>
            <span class="rarity common">Comum</span>
          </div>
        </div>
        
        <div class="achievement-slot unlocked" data-rarity="epic">
          <div class="achievement-icon azure-icon">☁️</div>
          <div class="achievement-info">
            <h4>Cloud Master</h4>
            <p>Especialista em Azure e AI</p>
            <span class="achievement-xp">+300 XP</span>
            <span class="rarity epic">Épico</span>
          </div>
        </div>
        
        <!-- Slots bloqueados -->
        <div class="achievement-slot locked">
          <div class="achievement-icon locked-icon">🔒</div>
          <div class="achievement-info">
            <h4>???</h4>
            <p>Conquista misteriosa</p>
            <span class="rarity unknown">Desconhecido</span>
          </div>
        </div>
        
        <div class="achievement-slot locked">
          <div class="achievement-icon locked-icon">🔒</div>
          <div class="achievement-info">
            <h4>???</h4>
            <p>Próxima conquista</p>
            <span class="rarity unknown">Desconhecido</span>
          </div>
        </div>
        
        <div class="achievement-slot locked">
          <div class="achievement-icon locked-icon">🔒</div>
          <div class="achievement-info">
            <h4>???</h4>
            <p>Meta futura</p>
            <span class="rarity unknown">Desconhecido</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.works-app {
  padding: 20px;
  height: 100%;
  background: transparent; /* remove filled background, keep border as container */
  overflow-y: auto;
  border: 3px solid #333;
  border-radius: 12px;
}

.works-header {
  text-align: center;
  margin-bottom: 25px;
}

.works-image {
  display: block;
  width: 96px;
  height: 96px;
  object-fit: contain;
  margin: 0 auto 8px;
}

.works-header h2 {
  font-size: 22px;
  color: white;
  margin: 0;
  font-weight: bold;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
}

.achievements-gallery {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.gallery-header {
  background: rgba(255, 255, 255, 0.95);
  border-radius: 12px;
  padding: 15px;
  border: 3px solid #333;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

.stats {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 12px;
  font-weight: bold;
  color: #333;
}

.achievement-counter {
  color: #FFD700;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
}

.xp-counter {
  color: #9B59B6;
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
}

.achievements-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 8px;
}

.achievement-slot {
  background: rgba(255, 255, 255, 0.95);
  border-radius: 12px;
  padding: 12px 8px;
  border: 3px solid #333;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  text-align: center;
  transition: all 0.3s;
  position: relative;
  overflow: hidden;
}

.achievement-slot.unlocked:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.3);
}

.achievement-slot.unlocked::before {
  content: '';
  position: absolute;
  top: 0;
  left: -100%;
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.8), transparent);
  animation: shine 3s infinite;
}

@keyframes shine {
  0% { left: -100%; }
  50% { left: 100%; }
  100% { left: 100%; }
}

.achievement-slot.locked {
  opacity: 0.5;
  background: rgba(128, 128, 128, 0.3);
}

.achievement-icon {
  width: 40px;
  height: 40px;
  margin: 0 auto 8px;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 20px;
  border: 2px solid #333;
  position: relative;
}

/* Ícones específicos com cores pixel art */
.ceo-icon { background: linear-gradient(45deg, #FFD700, #FFA500); }
.fullstack-icon { background: linear-gradient(45deg, #4169E1, #1E90FF); }
.international-icon { background: linear-gradient(45deg, #32CD32, #228B22); }
.gamedev-icon { background: linear-gradient(45deg, #FF1493, #DC143C); }
.database-icon { background: linear-gradient(45deg, #8A2BE2, #4B0082); }
.chef-icon { background: linear-gradient(45deg, #FF6347, #FF4500); }
.artist-icon { background: linear-gradient(45deg, #FF69B4, #DA70D6); }
.multilingual-icon { background: linear-gradient(45deg, #00CED1, #20B2AA); }
.student-icon { background: linear-gradient(45deg, #FFA07A, #FA8072); }
.logistics-icon { background: linear-gradient(45deg, #DDA0DD, #D8BFD8); }
.service-icon { background: linear-gradient(45deg, #F0E68C, #BDB76B); }
.azure-icon { background: linear-gradient(45deg, #87CEEB, #4682B4); }
.locked-icon { 
  background: #666; 
  color: #999;
  animation: pulse 2s infinite;
}

@keyframes pulse {
  0%, 100% { opacity: 0.5; }
  50% { opacity: 0.8; }
}

.achievement-info h4 {
  font-size: 11px;
  color: #333;
  margin: 0 0 4px 0;
  font-weight: bold;
  line-height: 1.2;
}

.achievement-info p {
  font-size: 9px;
  color: #555;
  margin: 0 0 6px 0;
  line-height: 1.1;
}

.achievement-xp {
  display: block;
  font-size: 8px;
  color: #9B59B6;
  font-weight: bold;
  margin-bottom: 4px;
}

.rarity {
  display: block;
  font-size: 7px;
  font-weight: bold;
  padding: 2px 4px;
  border-radius: 4px;
  text-transform: uppercase;
}

.rarity.legendary { background: #FFD700; color: #333; }
.rarity.epic { background: #9B59B6; color: white; }
.rarity.rare { background: #4169E1; color: white; }
.rarity.uncommon { background: #32CD32; color: white; }
.rarity.common { background: #808080; color: white; }
.rarity.unknown { background: #333; color: #999; }

@media (max-width: 480px) {
  .achievements-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 6px;
  }
  
  .achievement-slot {
    padding: 8px 4px;
  }
  
  .achievement-icon {
    width: 32px;
    height: 32px;
    font-size: 16px;
  }
  
  .achievement-info h4 {
    font-size: 10px;
  }
  
  .achievement-info p {
    font-size: 8px;
  }
  
  .stats {
    flex-direction: column;
    gap: 5px;
    font-size: 11px;
  }
}
</style>