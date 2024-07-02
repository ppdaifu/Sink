<template>
  <main class="flex flex-col justify-center items-center min-h-screen overflow-hidden">
    <!-- 显示有超链接的提示语 -->
    <div class="text-white dark:text-black">
      <p class="text-center">链接打不开，请<a :href="supportLink" target="_blank" class="underline">联系客服</a>。</p>
      <p class="text-center">Link unavailable, please <a :href="supportLink" target="_blank" class="underline">contact us</a>.</p>
    </div>
  </main>
</template>

<script>
export default {
  head() {
    return {
      title: 'daifu link'
    }
  },
  data() {
    return {
      supportLink: '' // Initialize as an empty string
    }
  },
  mounted() {
    // Set supportLink when component is mounted
    const domainParts = window.location.host.split('.');
    domainParts.shift(); // Remove the first part
    const mainDomain = domainParts.join('.');
    this.supportLink = `https://kefu.${mainDomain}`;
  }
}
</script>

<style scoped>
.text-center {
  text-align: center;
}
.text-white {
  color: white;
}
.dark .text-white {
  color: white; /* Ensure that text is white in dark mode */
}
.dark .text-black {
  color: black; /* Ensure that text is black in dark mode */
}
.min-h-screen {
  min-height: 100vh; 
}
.underline {
  text-decoration: underline;
}
.overflow-hidden {
  overflow: hidden; /* Disable scrolling */
}
</style>
