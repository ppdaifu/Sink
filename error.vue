<template>
  <div>
    <!-- 页眉 -->
    <header class="header">
      <h1>Welcome to Our Service</h1>
    </header>

    <div class="w-full h-full max-w-[600px] mx-auto p-4">
      <div class="text-center">
        <!-- 调整字体大小 -->
        <p class="text-2.5xl mb-2 text-gray-800 dark:text-gray-200">当前链接已失效，请咨询客服获取新链接。</p>
        <p class="text-2.5xl text-gray-800 dark:text-gray-200">Link expired, please contact us.</p>
      </div>
      <div class="faq">
        <button class="accordion" @click="toggleAccordion(0)">Q：链接有效期多久？ <span v-if="activeAccordion === 0">-</span><span v-else>+</span></button>
        <div v-show="activeAccordion === 0" class="panel">
          <p>30分钟。确定要下单时客服会发新的付款链接。</p>
        </div>
        <button class="accordion" @click="toggleAccordion(1)">Q：为什么链接会过期？ <span v-if="activeAccordion === 1">-</span><span v-else>+</span></button>
        <div v-show="activeAccordion === 1" class="panel">
          <p>短时间频繁收款可能触发平台风控，顾客付款时会提示风险，为避免这种情况，我们使用不同账户轮换收款，每次付款都会发全新链接。</p>
        </div>
        <button class="accordion" @click="toggleAccordion(2)">Q：联系不上了怎么办？ <span v-if="activeAccordion === 2">-</span><span v-else>+</span></button>
        <div v-show="activeAccordion === 2" class="panel">
          <p>防止失联，可<a href="https://kefu.ofdai.com" target="_blank" rel="noopener noreferrer">点击这里联系备用客服</a>，或咨询邮箱 panpay#msn.com (replace # with @)</p>
        </div>
      </div>
    </div>

    <!-- 页脚 -->
    <footer class="footer">
      <p>&copy; 2024 Our Company. All rights reserved.</p>
    </footer>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const activeAccordion = ref(null);

const toggleAccordion = (index) => {
  activeAccordion.value = activeAccordion.value === index ? null : index;
};
</script>

<style scoped>
.header, .footer {
  text-align: center;
  padding: 20px;
  font-size: 1.25rem;
}
.accordion {
  background-color: #e5e5e5;
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
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 10px;
}
.accordion:hover, .accordion:focus {
  background-color: #ddd;
}
.panel {
  padding: 20px;
  text-align: left;
  font-size: 16px;
  line-height: 1.5;
  display: none;
}
.panel p {
  margin: 0;
}
.dark .accordion {
  background-color: #555;
  color: #f5f5f5;
}
.dark .accordion:hover, .dark .accordion:focus {
  background-color: #666;
}
</style>
