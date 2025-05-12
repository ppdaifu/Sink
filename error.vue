<script setup>
import { ref } from 'vue';

const isQRVisible = ref(false);

const showQRCode = () => {
  isQRVisible.value = !isQRVisible.value;
};
</script>

<template>
  <NuxtLayout name="default">
    <div class="urgent-contact-container">
      <div class="message">
        <h1 class="title">紧急联系客服说明 <span class="subtitle">Emergency Contact</span></h1>
      </div>
      <div class="instruction-list">
        <div class="instruction-item">
          <p>企业微信客服号于<strong>5月12日</strong>被临时限制，请添加下方新的客服微信号。</p>
          <p class="en-text">Our WeCom accounts were limited on <strong>12 May</strong>. Please add the new CS below.</p>
        </div>
        <div class="instruction-item">
          <p>服务全球客户，每日在线12小时，人工接单需要时间，无法秒回消息。</p>
          <p class="en-text">We're online 12 hours a day; replies may take time.</p>
        </div>
      </div>
      <button class="btn" @click="showQRCode">
        显示客服二维码
        <span class="en-text">Show QR</span>
      </button>
      <div v-if="isQRVisible" class="qr-container">
        <a href="https://kefu.ofdai.com/static/wecom-kf-qr-ppdaifu.webp" target="_blank" rel="noopener noreferrer">
          <img class="qr-code" src="https://kefu.ofdai.com/static/wecom-kf-qr-ppdaifu.webp" alt="客服二维码">
        </a>
      </div>
    </div>
  </NuxtLayout>
</template>

<style scoped>
.urgent-contact-container {
  max-width: 600px;
  margin: 0 auto;
  padding: 40px;
  transition: background-color 0.3s, color 0.3s;
}

.message {
  margin-bottom: 40px;
  text-align: center;
}

.title {
  font-size: 1.5rem;
  font-weight: 600;
  margin-bottom: 10px;
  color: var(--text-color);
}

.subtitle {
  font-size: 1.25rem;
  font-weight: 400;
  color: var(--text-color);
  margin-left: 10px;
}

.instruction-list {
  margin-bottom: 30px;
}

.instruction-item {
  margin-bottom: 20px;
  padding: 15px;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  background-color: var(--panel-bg);
  text-align: left;
  font-size: 16px;
  line-height: 1.5;
  color: var(--text-color);
}

.instruction-item p {
  margin: 0 0 8px 0;
}

.en-text {
  font-size: 14px;
  color: var(--text-color);
  opacity: 0.8;
}

.btn {
  background-color: var(--accordion-bg);
  border: none;
  outline: none;
  cursor: pointer;
  padding: 15px 20px;
  width: 100%;
  text-align: center;
  font-size: 18px;
  font-weight: 600;
  color: var(--text-color);
  border-radius: 8px;
  transition: background-color 0.3s ease;
  display: flex;
  justify-content: center;
  align-items: center;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.btn:hover {
  background-color: var(--accordion-hover-bg);
}

.btn .en-text {
  font-size: 14px;
  margin-left: 10px;
  opacity: 0.8;
}

.qr-container {
  margin-top: 20px;
  text-align: center;
  padding: 15px;
  border-radius: 8px;
  background-color: var(--panel-bg);
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.qr-code {
  max-width: 200px;
  height: auto;
  border-radius: 4px;
}

a {
  color: var(--link-color);
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}

:root {
  --bg-color: #ffffff;
  --text-color: #333333;
  --accordion-bg: #f0f0f0;
  --accordion-hover-bg: #e0e0e0;
  --panel-bg: #ffffff;
  --link-color: #007bff;
}

:root.dark-mode {
  --bg-color: #2c2c2c;
  --text-color: #f5f5f5;
  --accordion-bg: #3c3c3c;
  --accordion-hover-bg: #4c4c4c;
  --panel-bg: #2c2c2c;
  --link-color: #66aaff;
}
</style>