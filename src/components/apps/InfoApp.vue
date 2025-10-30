<script setup lang="ts">
</script>

<template>
  <div class="info-app">
    <div class="info-header">
      <img class="info-image" src="/ponto-interrogacao-26286.gif" alt="info" />
      <h2>Information</h2>
    </div>
    
    <div class="info-content">
      <div class="info-card">
        <h3>💼 Experiências Profissionais</h3>
        <div class="experience-timeline">
          <div class="exp-item">
            <h4>CEO - Its High Play LTDA</h4>
            <p class="period">07/2025 - Atual | Palhoça, SC</p>
            <p>Fundador e CEO da empresa de consultoria e serviços digitais, liderando desenvolvimento de jogos com expertise artística e técnica.</p>
          </div>
          <div class="exp-item">
            <h4>Programador FullStack - IT VALLEY SCHOOL</h4>
            <p class="period">08/2025 | Home Office, Canadá</p>
            <p>Desenvolvimento com AI, Azure e automação para otimizar processos lógicos, webapps e integração de sistemas.</p>
          </div>
          <div class="exp-item">
            <h4>Assistente de Expedição - Magalu</h4>
            <p class="period">10/2024 - 03/2025 | São José, SC</p>
            <p>Atendimento ao cliente, processamento de entregas, organização logística e análise de dados.</p>
          </div>
          <div class="exp-item">
            <h4>Consultor de Análise de BD - Ubisafe</h4>
            <p class="period">04/2023 - 11/2023 | São José, SC</p>
            <p>Análise de banco de dados, melhoria de sistemas e criação de dashboards interativos.</p>
          </div>
        </div>
      </div>
      
      <div class="info-card">
        <h3>🎓 Formação Acadêmica</h3>
        <div class="education-list">
          <div class="edu-item">
            <h4>Tecnólogo em Produção Multimídia - IFSC</h4>
            <p class="period">03/2024 - Cursando | Palhoça, SC</p>
            <p>Animação (Motion, 2D, 3D), marketing, design e produção audiovisual.</p>
          </div>
          <div class="edu-item">
            <h4>Desenvolvimento de Jogos - Saga</h4>
            <p class="period">10/2023 - 03/2025 | EAD</p>
            <p>Unreal Engine 5, Photoshop e Blender para desenvolvimento de jogos.</p>
          </div>
          <div class="edu-item">
            <h4>ADS - Análise e Desenvolvimento de Sistemas</h4>
            <p class="period">02/2019 - 12/2021 | Sesi-Senai, SC</p>
            <p>Programação, banco de dados e criação de software.</p>
          </div>
        </div>
      </div>
      
      <div class="info-card">
        <h3>🛠️ Habilidades Técnicas</h3>
        <div class="skills-section">
          <div class="skill-category">
            <h5>Programação</h5>
            <div class="tech-list">
              <span class="tech-item">C#/.NET</span>
              <span class="tech-item">JavaScript</span>
              <span class="tech-item">TypeScript</span>
              <span class="tech-item">Python</span>
              <span class="tech-item">Java</span>
              <span class="tech-item">C++</span>
            </div>
          </div>
          <div class="skill-category">
            <h5>Web Development</h5>
            <div class="tech-list">
              <span class="tech-item">React</span>
              <span class="tech-item">Next.js</span>
              <span class="tech-item">Node.js</span>
              <span class="tech-item">Vue.js</span>
              <span class="tech-item">MongoDB</span>
              <span class="tech-item">PostgreSQL</span>
            </div>
          </div>
          <div class="skill-category">
            <h5>Game Development</h5>
            <div class="tech-list">
              <span class="tech-item">Unreal Engine</span>
              <span class="tech-item">Unity</span>
              <span class="tech-item">Godot</span>
              <span class="tech-item">Blender</span>
              <span class="tech-item">ZBrush</span>
            </div>
          </div>
          <div class="skill-category">
            <h5>Design & Arte</h5>
            <div class="tech-list">
              <span class="tech-item">Photoshop</span>
              <span class="tech-item">Illustrator</span>
              <span class="tech-item">After Effects</span>
              <span class="tech-item">Premiere</span>
              <span class="tech-item">UX Design</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.info-app {
  padding: 20px;
  height: 100%;
  background: transparent;
  overflow-y: auto;
  border: 3px solid #333;
  border-radius: 12px;
}

.info-header {
  text-align: center;
  margin-bottom: 25px;
}

.info-image {
  display: block;
  width: 96px;
  height: 96px;
  object-fit: contain;
  margin: 0 auto 8px;
}

.info-header h2 {
  font-size: 22px;
  color: white;
  margin: 0;
  font-weight: bold;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
}

.info-content {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.info-card {
  background: rgba(255, 255, 255, 0.95);
  border-radius: 15px;
  padding: 20px;
  border: 3px solid #333;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.info-card h3 {
  font-size: 18px;
  color: #333;
  margin: 0 0 15px 0;
  font-weight: bold;
}

.info-card p {
  color: #555;
  line-height: 1.6;
  margin: 0;
  font-size: 14px;
}

.tech-list {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.tech-item {
  background: #4ECDC4;
  color: white;
  padding: 6px 12px;
  border-radius: 20px;
  font-size: 12px;
  font-weight: bold;
  border: 2px solid #333;
}

.feature-list {
  margin: 0;
  padding: 0;
  list-style: none;
}

.feature-list li {
  padding: 8px 0;
  color: #555;
  font-size: 14px;
  border-bottom: 1px solid #eee;
}

.feature-list li:last-child {
  border-bottom: none;
}

.version-info {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.version-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.version-label {
  color: #666;
  font-weight: bold;
  font-size: 14px;
}

.experience-timeline, .education-list {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.exp-item, .edu-item {
  border-left: 3px solid #4ECDC4;
  padding-left: 15px;
  margin-bottom: 15px;
}

.exp-item:last-child, .edu-item:last-child {
  margin-bottom: 0;
}

.exp-item h4, .edu-item h4 {
  color: #333;
  margin: 0 0 5px 0;
  font-size: 15px;
  font-weight: bold;
}

.exp-item .period, .edu-item .period {
  color: #666;
  font-size: 12px;
  font-weight: bold;
  margin: 0 0 8px 0;
}

.exp-item p:last-child, .edu-item p:last-child {
  color: #555;
  font-size: 13px;
  line-height: 1.4;
  margin: 0;
}

.skills-section {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.skill-category h5 {
  color: #333;
  margin: 0 0 8px 0;
  font-size: 14px;
  font-weight: bold;
}

.skill-category .tech-list {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
}

.skill-category .tech-item {
  font-size: 11px;
  padding: 4px 8px;
}
</style>