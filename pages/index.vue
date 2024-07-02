<template>
  <main class="flex flex-col justify-center items-center min-h-screen overflow-hidden">
    <!-- 显示有超链接的提示语 -->
    <div class="text-center text-link">
      <p>链接打不开，请<a :href="supportLink" target="_blank" class="underline">联系客服</a>。</p>
      <p>Link unavailable, please <a :href="supportLink" target="_blank" class="underline">contact us</a>.</p>
    </div>
  </main>
</template>

<script>
export default {
  head() {
    return {
      title: 'link'
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
</style>
