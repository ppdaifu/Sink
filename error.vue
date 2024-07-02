<script setup>
</script>

<template>
  <NuxtLayout name="default">
    <div
      class="w-full h-full max-w-[600px] mx-auto flex items-center justify-center text-center"
    >
      <div class="text-white dark:text-black">
        <p>当前链接已失效，请咨询客服获取新链接。</p>
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
</style>
