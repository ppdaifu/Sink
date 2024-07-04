<template>
  <NuxtLayout name="default">
    <div class="container">
      <div class="header">
        <p>链接已失效，请找客服获取新链接。</p>
        <p>Link expired, please contact us.</p>
      </div>
      <div class="faq">
        <button class="accordion" @click="toggleAccordion(0)">{{ activeAccordion === 0 ? '-' : '+' }} Q：链接有效期多久？</button>
        <div class="panel" v-if="activeAccordion === 0">
          <p>30分钟。确定要下单时客服会发新的付款链接。</p>
        </div>
        <button class="accordion" @click="toggleAccordion(1)">{{ activeAccordion === 1 ? '-' : '+' }} Q：为什么链接会过期？</button>
        <div class="panel" v-if="activeAccordion === 1">
          <p>短时间频繁收款可能触发平台风控，顾客付款时会提示风险，为避免这种情况，我们使用不同账户轮换收款，每次付款都会发全新链接。</p>
        </div>
        <button class="accordion" @click="toggleAccordion(2)">{{ activeAccordion === 2 ? '-' : '+' }} Q：联系不上了怎么办？</button>
        <div class="panel" v-if="activeAccordion === 2">
          <p>防止失联，可<a href="https://kefu.ofdai.com" target="_blank" rel="noopener noreferrer">点击这里联系备用客服</a>，或咨询邮箱 panpay#msn.com(replace # with @)</p>
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
.container {
  max-width: 600px;
  margin: auto;
  padding: 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.header p {
  font-size: 3rem; /* 增大字体 */
  text-align: center;
  color: #333;
  margin-bottom: 1rem;
}
.dark .header p {
  color: #f5f5f5;
}
.accordion {
  background-color: #e5e5e5;
  color: #333;
  cursor: pointer;
  padding: 20px;
  width: calc(100% - 40px); /* 解决宽度变化问题 */
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
.accordion:hover {
  background-color: #ddd;
}
.dark .accordion {
  background-color: #4a4a4a; /* 改进暗夜模式下的背景色 */
  color: #f5f5f5;
}
.dark .accordion:hover {
  background-color: #5a5a5a;
}
.panel {
  padding: 0 20px;
  text-align: left;
  font-size: 16px;
  line-height: 1.5;
  margin-top: 10px;
  margin-bottom:
