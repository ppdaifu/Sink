<template>
  <div class="flex flex-col min-h-screen justify-center items-center">
    <main class="flex flex-col justify-center items-center flex-grow text-center">
      <!-- 图片放置在提示语上方 -->
      <img src="/assets/images/404.svg" alt="404 Image" />
      
      <!-- 显示有超链接的提示语 -->
      <div class="text-link mt-4">
        <p>链接无效，请<a :href="supportLink" target="_blank" class="underline">联系客服</a>。</p>
        <p>Link unavailable, please <a :href="supportLink" target="_blank" class="underline">contact us</a>.</p>
      </div>
    </main>
  </div>
</template>

