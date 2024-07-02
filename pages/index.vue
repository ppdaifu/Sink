<template>
  <main class="flex flex-col justify-center items-center min-h-screen">
    <p class="text-center text-white">链接打不开，请联系客服。</p>
    <p class="text-center text-white">Link unavailable, contact us.</p>
    <!-- Moved this inside the NuxtLayout to avoid duplication -->
    <NuxtLayout name="default">
      <div class="text-white dark:text-black">
        <p>链接打不开，请<a :href="supportLink" target="_blank" class="underline">联系客服</a>。</p>
        <p>Link unavailable, please <a :href="supportLink" target="_blank" class="underline">contact us</a>.</p>
      </div>
    </NuxtLayout>
  </main>
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
    this.supportLink = `https://kefu.${window.location.host}`;
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
  color: white; /* Fixed color styling */
}
.dark .text-black {
  color: black;
}
.min-h-screen {
  min-height: 100vh;
}
.underline {
  text-decoration: underline;
}
</style>
