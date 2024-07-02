<script setup>
</script>

<template>
  <NuxtLayout name="default">
    <div
      class="w-full h-full max-w-[600px] mx-auto flex items-center justify-center text-center p-4"
    >
      <div class="text-lg text-gray-800 dark:text-gray-200">
        <p class="mb-2">当前链接已失效，请咨询客服获取新链接。</p>
        <p>Link expired, please contact us.</p>
      </div>
    </div>
  </NuxtLayout>
</template>

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
.text-lg {
  font-size: 1.125rem; /* 18px */
}
.mb-2 {
  margin-bottom: 0.5rem; /* 8px */
}
</style>
