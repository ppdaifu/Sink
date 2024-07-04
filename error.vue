<template>
  <NuxtLayout name="default">
    <div
      class="w-full h-full max-w-[600px] mx-auto flex items-center justify-center text-center p-4"
    >
      <div class="text-lg text-gray-800 dark:text-gray-200">
        <p class="mb-2">当前链接已失效，请咨询客服获取新链接。</p>
        <p>Link expired, please contact us.</p>
        <div class="faq">
          <button class="accordion" @click="toggleAccordion(0)">Q：链接有效期多久？</button>
          <div class="panel" v-if="activeAccordion === 0">
            <p>30分钟。确定要下单时客服会发新的付款链接。</p>
          </div>
          <button class="accordion" @click="toggleAccordion(1)">Q：为什么链接会过期？</button>
          <div class="panel" v-if="activeAccordion === 1">
            <p>短时间频繁收款可能触发平台风控，顾客付款时会提示风险，为避免这种情况，我们使用不同账户轮换收款，每次付款都会发全新链接。</p>
          </div>
          <button class="accordion" @click="toggleAccordion(2)">Q：联系不上了怎么办？</button>
          <div class="panel" v-if="activeAccordion === 2">
            <p>防止失联，可<a href="https://kefu.ofdai.com" target="_blank" rel="noopener noreferrer">点击这里联系备用客服</a>，或咨询邮箱 panpay#msn.com(replace # with @)</p>
          </div>
        </div>
      </div>
    </div>
  </NuxtLayout>
</template>

<script setup>
import { ref } from 'vue';

const activeAccordion = ref(null);

const toggleAccordion = (index) => {
  activeAccordion.value = activeAccordion.value === index ? null : index;
};
</script>

<style scoped>
.text-center {
  text-align: center;
}
.text-white {
  color: white;
}
.dark .text-black, .dark .text-gray-800 {
  color: black;
}
.dark .dark\\:text-gray-200 {
  color: #f5f5f5;
}
.text-lg {
  font-size: 1.125rem; /* 18px */
}
.mb-2 {
  margin-bottom: 0.5rem; /* 8px */
}
.accordion {
  background-color: #f5f5f5;
  color: #333;
  cursor: pointer;
  padding: 20px;
  width: 100%;
  text-align: left;
  font-size: 18px;
  font-weight: 600;
  border: none;
  outline: none;
  transition: background-color 0.3s ease;
  position: relative;
  margin-top: 10px;
}
.accordion:hover {
  background-color: #e5e5e5;
}
.dark .accordion {
  background-color: #555;
  color: #f5f5f5;
}
.dark .accordion:hover {
  background-color: #666;
}
.panel {
  transition: max-height 0.3s ease;
  padding: 0 20px;
  text-align: left;
  font-size: 16px;
  line-height: 1.5;
  margin-top: 10px;
  margin-bottom: 10px;
}
</style>
