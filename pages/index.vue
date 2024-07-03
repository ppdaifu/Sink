<template>
  <div class="min-h-screen flex items-center justify-center">
    <main>
      <!-- 图片放置在提示语上方 -->
      <img src="/assets/images/404.svg" alt="404 Image" class="w-1/2 md:w-1/3 mb-4 mx-auto" />
      
      <!-- 显示有超链接的提示语 -->
      <div class="text-link text-center">
        <p>链接無效，请<a :href="supportLink" target="_blank" class="underline">联系客服</a>。</p>
        <p>Link unavailable, please <a :href="supportLink" target="_blank" class="underline">contact us</a>.</p>
      </div>
    </main>
  </div>
</template>

<script>
export default {
  data() {
    return {
      supportLink: ''
    }
  },
  mounted() {
    const domainParts = window.location.host.split('.');
    domainParts.shift(); 
    const mainDomain = domainParts.join('.');
    this.supportLink = `https://kefu.${mainDomain}`;
  }
}
</script>

<style scoped>
.text-link {
  color: var(--text-color);
}
.dark .text-link {
  color: white;
}
.light .text-link {
  color: black;
}
body {
  --text-color: black;
}
.dark body {
  --text-color: white;
}
</style>
