<template>
  <main class="flex flex-col justify-center items-center min-h-screen">
    <p class="text-center text-white">链接打不开，请联系客服。</p>
    <p class="text-center text-white">Link unavailable, contact us.</p>
  </main>
  <NuxtLayout name="default">
    <main class="flex flex-col items-center justify-center flex-grow py-10">
      <div class="text-white dark:text-black">
        <p>链接打不开，请<a :href="supportLink" target="_blank" class="underline">联系客服</a>。</p>
        <p>Link unavailable, please <a :href="supportLink" target="_blank" class="underline">contact us</a>.</p>
      </div>
    </main>
  </NuxtLayout>
</template>

<script>
export default {
  head() {
    return {
      title: 'daifu'
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
</style>
