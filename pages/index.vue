<template>
  <NuxtLayout name="default">
    <div class="w-full h-full max-w-[600px] mx-auto flex flex-col items-center justify-center text-center">
      <header class="w-full bg-gray-800 text-white p-4">
        <!-- 这里是页眉的内容 -->
      </header>
      <main class="flex flex-col items-center justify-center flex-grow py-10">
        <div class="text-white dark:text-black">
          <p>链接打不开，请<a :href="supportLink" target="_blank" class="underline">联系客服</a>。</p>
          <p>Link unavailable, please <a :href="supportLink" target="_blank" class="underline">contact us</a>.</p>
        </div>
      </main>
      <footer class="w-full bg-gray-800 text-white p-4">
        <!-- 这里是页脚的内容 -->
      </footer>
    </div>
  </NuxtLayout>
</template>

<script setup>
import { ref, computed } from 'vue'

const currentHost = ref(window.location.host)
const supportLink = computed(() => `https://kefu.${currentHost}`)
</script>

<style scoped>
.text-center {
  text-align: center;
}
.text-white {
  color: white;
}
.dark .text-black {
  color: black;
}
.underline {
  text-decoration: underline;
}
</style>
