<template>
  <div class="flex flex-col min-h-screen">
    <main class="flex flex-col justify-center items-center flex-grow overflow-hidden text-center">
      <!-- 图片放置在提示语上方 -->
      <img src="/assets/images/404.svg" alt="404 Image" class="w-1/2 md:w-1/3 mb-4" />
      
      <!-- 显示有超链接的提示语 -->
      <div class="text-link">
        <p>链接打不开，请<a :href="supportLink" target="_blank" class="underline">联系客服</a>。</p>
        <p>Link unavailable, please <a :href="supportLink" target="_blank" class="underline">contact us</a>.</p>
      </div>
    </main>
    <!-- 页脚 -->
    <footer class="bg-gray-800 text-white py-4 text-center">
      <!-- 页脚内容 -->
      <p>页脚内容</p>
    </footer>
  </div>
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
.overflow-hidden {
  overflow: hidden; /* Disable scrolling */
}
body {
  --text-color: black; /* Default text color */
}
.dark body {
  --text-color: white; /* Text color for dark mode */
}
footer {
  background-color: #333; /* Dark background for footer */
  color: white; /* White text color for footer */
  padding: 1rem; /* Padding for footer */
  text-align: center; /* Center align footer text */
}
</style>
