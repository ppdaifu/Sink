<template>
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
.dark .text-black {
  color: black;
}
.underline {
  text-decoration: underline;
}
</style>
