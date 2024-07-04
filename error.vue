<script setup>
import { ref, onMounted } from 'vue';

const accordions = ref([
  {
    question: "Q：链接有效期多久？",
    answer: "30分钟。确定要下单时客服会发新的付款链接。",
    isOpen: false
  },
  {
    question: "Q：为什么链接会过期？",
    answer: "短时间频繁收款可能触发平台风控，顾客付款时会提示风险，为避免这种情况，我们使用不同账户轮换收款，每次付款都会发全新链接。",
    isOpen: false
  },
  {
    question: "Q：联系不上了怎么办？",
    answer: "防止失联，可<a href=\"https://kefu.ofdai.com\" target=\"_blank\" rel=\"noopener noreferrer\">点击这里联系备用客服</a>，或咨询邮箱 panpay#msn.com(replace # with @)",
    isOpen: false
  }
]);

const toggleAccordion = (index) => {
  accordions.value[index].isOpen = !accordions.value[index].isOpen;
};

onMounted(() => {
  // The dark mode toggle is assumed to be handled by your existing layout
});
</script>

<template>
  <NuxtLayout name="default">
    <div class="expired-link-container">
      <h1 class="title">403 Error</h1>
      <h2 class="subtitle">链接已过期，请联系客服索取新链接。</h2>
      <div class="faq">
        <div v-for="(item, index) in accordions" :key="index" class="accordion-item">
          <button 
            class="accordion" 
            :class="{ 'active': item.isOpen }" 
            @click="toggleAccordion(index)"
          >
            {{ item.question }}
          </button>
          <div class="panel" :class="{ 'open': item.isOpen }">
            <p v-html="item.answer"></p>
          </div>
        </div>
      </div>
    </div>
  </NuxtLayout>
</template>

<style scoped>
.expired-link-container {
  max-width: 600px;
  margin: 0 auto;
  padding: 40px;
  background-color: var(--bg-color);
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  text-align: center;
  transition: background-color 0.3s, color 0.3s;
}

.title {
  font-size: 4rem;
  font-weight: 700;
  margin-bottom: 20px;
  color: var(--text-color);
}

.subtitle {
  font-size: 2rem;
  font-weight: 400;
  margin-bottom: 40px;
  color: var(--text-color);
}

.accordion {
  background-color: var(--accordion-bg);
  border: none;
  outline: none;
  cursor: pointer;
  padding: 20px;
  width: 100%;
  text-align: left;
  font-size: 18px;
  font-weight: 600;
  color: var(--text-color);
  transition: background-color 0.3s ease;
  position: relative;
  border-radius: 8px;
  margin-bottom: 10px;
}

.accordion:hover {
  background-color: var(--accordion-hover-bg);
}

.accordion::after {
  content: '+';
  position: absolute;
  right: 20px;
  font-size: 24px;
  font-weight: 700;
  color: var(--text-color);
  transition: transform 0.3s ease;
}

.accordion.active::after {
  content: '-';
  transform: rotate(180deg);
}

.panel {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.3s ease;
  padding: 0 20px;
  text-align: left;
  font-size: 16px;
  line-height: 1.5;
  margin-top: 10px;
  margin-bottom: 10px;
  color: var(--text-color);
}

.panel.open {
  max-height: 200px;
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
  --link-color: #007bff;
}

:root.dark-mode {
  --bg-color: #2c2c2c;
  --text-color: #f5f5f5;
  --accordion-bg: #3c3c3c;
  --accordion-hover-bg: #4c4c4c;
  --link-color: #66aaff;
}
</style>
