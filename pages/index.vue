<template>
  <div class="flex flex-col min-h-screen justify-center items-center">
    <main class="flex flex-col justify-center items-center flex-grow text-center">
      <!-- 图片放置在提示语上方 -->
      <img src="/assets/images/404.svg" alt="404 Image" class="w-1/2 md:w-1/3 mb-4" />
      
      <!-- 显示有超链接的提示语 -->
      <div class="text-link">
        <p>链接打不开，请<a :href="supportLink" target="_blank" class="underline">联系客服</a>。</p>
        <p>Link unavailable, please <a :href="supportLink" target="_blank" class="underline">contact us</a>.</p>
      </div>
    </main>
  </div>
</template>

<script>
export default {
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
.text-link {
  color: var(--text-color); /* Use a variable for text color */
}
.dark .text-link {
  color: white; /* Ensure that text is white in dark mode */
}
.light .text-link {
  color: black; /* Ensure that text is black in light mode */
}
.min-h-screen {
  min-height: 100vh; 
}
.underline {
  text-decoration: underline;
}
body {
  --text-color: black; /* Default text color */
}
.dark body {
  --text-color: white; /* Text color for dark mode */
}
html, body {
  height: 100%; /* Ensure the body takes the full height */
  margin: 0; /* Remove default margin */
}
</style>
