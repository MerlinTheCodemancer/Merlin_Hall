<script setup lang="ts">
import { computed, ref } from 'vue'
import paperLarge from '../../assets/paperPixelArtG.svg'
import crossboard from '../../assets/CrossboardPixelArt.svg'

const toEmail = 'merlin.thecodemecer@gmail.com'

const fromEmail = ref('')
const subject = ref('')
const message = ref('')
const attachmentName = ref<string | null>(null)

const mailtoHref = computed(() => {
  const subjectEncoded = encodeURIComponent(subject.value.trim())
  const bodyParts = [
    `From: ${fromEmail.value.trim() || '(não informado)'}`,
    '',
    message.value.trim(),
  ]

  if (attachmentName.value) {
    bodyParts.push('', `Anexo (selecionado no site): ${attachmentName.value}`)
  }

  const bodyEncoded = encodeURIComponent(bodyParts.join('\n'))
  return `mailto:${toEmail}?subject=${subjectEncoded}&body=${bodyEncoded}`
})

function onPickAttachment(event: Event) {
  const input = event.target as HTMLInputElement
  const file = input.files?.[0] ?? null
  attachmentName.value = file?.name ?? null
}

function onSend() {
  window.location.href = mailtoHref.value
}
</script>

<template>
  <div class="contact-app">
    <div class="contact-frame" :style="{ '--crossboard-url': `url(${crossboard})`, '--paper-url': `url(${paperLarge})` }">
      <div class="contact-inner">
        <header class="contact-header">
          <h2>Enviar Email</h2>
        </header>

        <form class="email-form" @submit.prevent="onSend">
          <div class="field">
            <label class="label">Para</label>
            <div class="readonly">{{ toEmail }}</div>
          </div>

          <div class="field">
            <label class="label" for="fromEmail">De</label>
            <input
              id="fromEmail"
              v-model="fromEmail"
              class="input"
              type="email"
              autocomplete="email"
              placeholder="seuemail@exemplo.com"
            />
          </div>

          <div class="field">
            <label class="label" for="subject">Assunto</label>
            <input id="subject" v-model="subject" class="input" type="text" placeholder="Assunto da mensagem" />
          </div>

          <div class="field field--message">
            <label class="label" for="message">Mensagem</label>
            <textarea
              id="message"
              v-model="message"
              class="textarea"
              rows="6"
              placeholder="Escreva sua mensagem..."
            />

            <div class="attach-row">
              <input id="attachment" class="attach-input" type="file" @change="onPickAttachment" />
              <label class="attach-row__button" for="attachment">Anexar</label>
              <span v-if="attachmentName" class="attach-row__name">{{ attachmentName }}</span>
              <span v-else class="attach-row__name attach-row__name--empty">Nenhum anexo</span>
            </div>
          </div>

          <button class="send-fab" type="submit" :title="'Enviar mensagem para ' + toEmail" aria-label="Enviar mensagem">
            <span class="send-fab__text">Enviar</span>
          </button>
        </form>
      </div>
    </div>
  </div>
</template>

<style scoped>
.contact-app {
  padding-left: 6px;
  padding-right: 6px;
  height: 100%;
  background: transparent;
  overflow-y: auto;
}

.contact-frame {
  position: relative;
  min-height: 100%;
  overflow: hidden;
  background-position: center;
  background-repeat: no-repeat;
  background-size: contain;
  background-image:var(--crossboard-url);
}

.contact-inner {
  position: relative;
  z-index: 1;
  padding-top: 85px;
  padding-left: 20px;
  padding-right: 30px;
  padding-bottom: 65px;
  display: flex;
  flex-direction: column;
  gap: 0px;
}

.contact-header h2 {
  margin: 0;
  position: relative;
  text-align: center;
  font-size: 32px;
  color: #ffffff;
  text-shadow: #1a1a1a 4px 4px 6px;
}

.contact-header p {
  margin: 4px 0 0 0;
  font-size: 11px;
  color: rgba(255, 255, 255, 0.85);
}

.email-form {
  position: relative;
  display: flex;
  flex-direction: column;
  gap: 0px;
  margin-top: 10px;
}

.field {
  display: grid;
  gap: 6px;
  margin-bottom: 12px;
}

.field--message {
  margin-bottom: 10px;
}

.label {
  font-size: 11px;
  font-weight: 800;
  color: #1a1a1a;
}

.readonly {
  padding: 8px 6px;
  background: rgba(73, 27, 0, 0.2);
  font-size: 10px;
  border-radius: 12px;
  border: none;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.input,
.textarea {
  width: 100%;
  border-radius: 12px;
  border: none;
  padding: 8px 6px;
  background: rgba(73, 17, 0, 0.2);
  font-size: 12px;
  outline: none;
}

.textarea {
  resize: vertical;
  min-height: 120px;
}

.textarea--message {
  margin-bottom: 10px;
}

.attach-row {
  font-family: Fipps-Regular;
  display: flex;
  align-items: center;
  gap: 10px;
  margin-top: -200px;
  margin: 20px;
}

.attach-input {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border: 0;
}

.attach-row__button {
  margin-top: 30px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  height: 34px;
  padding-left: 10px;
  padding-right: 10px;
  padding-bottom: 10px;
  border-radius: 10px;
  cursor: pointer;
  user-select: none;
  font-size: 10px;
  background: rgba(126, 40, 0, 0.5);
  color: #000000;
  border: 2px solid rgba(0, 0, 0, 0.35);
  transition: transform 0.15s ease, filter 0.15s ease;
}

.attach-row__button:hover {
  transform: translateY(-1px);
  filter: brightness(1.08);
}

.attach-row__button:active {
  transform: translateY(1px);
}

.attach-row__name {
  margin-top: 30px;
  min-width: 0;
  font-size: 10px;
  color: rgba(0, 0, 0, 0.92);
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
  padding-bottom: 10px;
}

.attach-row__name--empty {
  opacity: 0.8;
}


.send-fab {
  position: absolute;
  right: 20px;
  bottom: 30px;
  width: 60px;
  height: 60px;
  background: url('../../assets/BotaoEnvioPixelArt.svg') center/cover no-repeat;
  cursor: pointer;
  box-shadow: none;
  border: none;
}

.send-fab__text {
  padding-top: 40px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-weight: 900;
  font-size: 12px;
  color: #1a1a1a;
  letter-spacing: 0.02em;
}

.send-fab:hover {
  transform: translateY(-2px);
}

.send-fab:active {
  transform: translateY(1px);
}
</style>