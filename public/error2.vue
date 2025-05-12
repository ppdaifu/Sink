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
  accordions.value.forEach((item, i) => {
    item.isOpen = i === index ? !item.isOpen : false;
  });
};

onMounted(() => {
  document.title = "链接失效 - Link Expired";
});
</script>

<template>
  <NuxtLayout name="default">
    <div class="expired-link-container">
      <div class="message">
        <h1 class="title">链接已失效，请咨询客服获取新链接。</h1>
        <h2 class="subtitle">Link expired, please contact us.</h2>
      </div>
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
}

.accordion-item {
  margin-bottom: 15px;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  overflow: hidden;
}

.accordion {
  background-color: var(--accordion-bg);
  border: none;
  outline: none;
  cursor: pointer;
  padding: 15px 40px 15px 20px;
  width: 100%;
  text-align: left;
  font-size: 18px;
  font-weight: 600;
  color: var(--text-color);
  transition: background-color 0.3s ease;
  position: relative;
}

.accordion:hover {
  background-color: var(--accordion-hover-bg);
}

.accordion::after {
  content: '+';
  position: absolute;
  right: 20px;
  top: 50%;
  transform: translateY(-50%);
  font-size: 24px;
  font-weight: 700;
  color: var(--text-color);
  transition: transform 0.3s ease;
}

.accordion.active::after {
  transform: translateY(-50%) rotate(45deg);
}

.panel {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.3s ease-out, padding 0.3s ease-out, opacity 0.3s ease-out;
  padding: 0 20px;
  text-align: left;
  font-size: 16px;
  line-height: 1.5;
  color: var(--text-color);
  opacity: 0;
  background-color: var(--panel-bg);
}

.panel.open {
  max-height: 1000px;
  padding: 15px 20px;
  opacity: 1;
  transition: max-height 0.5s ease-in, padding 0.3s ease-in, opacity 0.5s ease-in;
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
