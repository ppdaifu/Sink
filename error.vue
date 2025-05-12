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
        <h1 class="title">紧急联系客服说明</h1>
        <p class="subtitle">Emergency Contact</p>
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
        <span>显示客服二维码</span>
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
  max-width: 500px;
  margin: 40px auto;
  padding: 30px;
  background-color: var(--bg-color);
  border-radius: 12px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
  transition: background-color 0.3s, color 0.3s;
}

.message {
  margin-bottom: 30px;
  text-align: center;
}

.title {
  font-size: 1.8rem;
  font-weight: 700;
  color: var(--text-color);
  margin: 0 0 10px 0;
}

.subtitle {
  font-size: 1.2rem;
  font-weight: 400;
  color: var(--text-color-light);
  margin: 0;
}

.instruction-list {
  margin-bottom: 30px;
}

.instruction-item {
  margin-bottom: 15px;
  padding: 12px 20px;
  background-color: var(--panel-bg);
  border-radius: 6px;
  color: var(--text-color);
  font-size: 16px;
  line-height: 1.6;
}

.instruction-item p {
  margin: 0 0 6px 0;
}

.en-text {
  font-size: 14px;
  color: var(--text-color-light);
  opacity: 0.8;
}

.btn {
  display: block;
  width: 100%;
  padding: 12px;
  background-color: var(--button-bg);
  border: none;
  border-radius: 8px;
  font-size: 1.1rem;
  font-weight: 600;
  color: var(--text-color);
  cursor: pointer;
  transition: background-color 0.3s ease;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
}

.btn:hover {
  background-color: var(--button-hover-bg);
}

.btn span {
  display: block;
}

.btn .en-text {
  font-size: 0.9rem;
  opacity: 0.8;
}

.qr-container {
  margin-top: 20px;
  text-align: center;
  padding: 15px;
  background-color: var(--panel-bg);
  border-radius: 8px;
}

.qr-code {
  max-width: 180px;
  height: auto;
  display: block;
  margin: 0 auto;
}

:root {
  --bg-color: #ffffff;
  --text-color: #333333;
  --text-color-light: #666666;
  --panel-bg: #f5f5f5;
  --button-bg: #e0e0e0;
  --button-hover-bg: #d0d0d0;
}

:root.dark-mode {
  --bg-color: #2c2c2c;
  --text-color: #ffffff;
  --text-color-light: #cccccc;
  --panel-bg: #3a3a3a;
  --button-bg: #4a4a4a;
  --button-hover-bg: #5a5a5a;
}
</style>