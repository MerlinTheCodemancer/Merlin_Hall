<script setup lang="ts">
</script>

<template>
  <div class="profile-app">
    <div class="profile-header">
      <img class="profile-image" src="/origami.gif" alt="profile" />
      <h2>Merlin Codemancer Profile</h2>
    </div>
    
    <div class="profile-content">
      <div class="profile-section">
        <h3>Quem sou eu?</h3>
        <p>Olá! Sou Marcelo Ferreira, um desenvolvedor apaixonado por jogos, animação e cultura desde criança. Esta paixão me levou ao aprendizado autodidata de programação e artes digitais, explorando áreas como concept art e modelagem 3D.</p>
        <p>Atualmente curso uma graduação que combina tecnologia e arte, com o objetivo de criar experiências criativas e ajudar pessoas através dos meus projetos.</p>
      </div>
      
      <div class="profile-section">
        <h3>Conquistas Especiais</h3>
        <div class="achievement-item">
          <span class="achievement-icon">🌍</span>
          <div>
            <h4>Experiência Internacional</h4>
            <p>Vivi com holandeses e outras nacionalidades europeias por 3 meses, tornando meu inglês fluente.</p>
          </div>
        </div>
        <div class="achievement-item">
          <span class="achievement-icon">🏆</span>
          <div>
            <h4>Masterchef Junior - 2016</h4>
            <p>Prêmio de Melhor Hambúrguer entre toda a escola fundamental.</p>
          </div>
        </div>
      </div>
      
      <div class="profile-section">
        <h3>Minha Jornada</h3>
        <p>Como CEO e fundador da <strong>Its High Play LTDA</strong>, lidero o desenvolvimento de jogos, combinando expertise artística e técnica. Isso me permite oferecer soluções independentes e abrangentes nas áreas de desenvolvimento de jogos, arte, programação e design.</p>
        <p>Minha experiência vai desde análise de banco de dados até desenvolvimento fullstack, sempre buscando criar experiências únicas e inovadoras.</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.profile-app {
  padding: 20px;
  height: 100%;
  background: linear-gradient(135deg, #FFD700 0%, #FFA500 100%);
}

.profile-header {
  text-align: center;
  margin-bottom: 30px;
}

.profile-image {
  display: block;
  width: 96px;
  height: 96px;
  object-fit: contain;
  margin: 0 auto 8px;
}

.profile-header h2 {
  font-size: 24px;
  color: #333;
  margin: 0;
  font-weight: bold;
}

.profile-content {
  display: flex;
  flex-direction: column;
  gap: 25px;
}

.profile-section {
  background: rgba(255, 255, 255, 0.9);
  padding: 20px;
  border-radius: 15px;
  border: 3px solid #333;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.profile-section h3 {
  font-size: 18px;
  color: #333;
  margin: 0 0 15px 0;
  font-weight: bold;
}

.profile-section p {
  color: #555;
  line-height: 1.5;
  margin: 0;
}

.skills-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.skill-tag {
  background: #4ECDC4;
  color: white;
  padding: 6px 12px;
  border-radius: 20px;
  font-size: 12px;
  font-weight: bold;
  border: 2px solid #333;
}

.experience-item {
  margin-bottom: 15px;
}

.experience-item:last-child {
  margin-bottom: 0;
}

.achievement-item {
  display: flex;
  align-items: flex-start;
  gap: 15px;
  margin-bottom: 15px;
}

.achievement-item:last-child {
  margin-bottom: 0;
}

.achievement-icon {
  font-size: 24px;
  flex-shrink: 0;
}

.achievement-item h4 {
  font-size: 16px;
  color: #333;
  margin: 0 0 5px 0;
}

.achievement-item p {
  color: #666;
  font-size: 13px;
  margin: 0;
  line-height: 1.4;
}
</style>