<template>
  <main class="flex flex-col items-center justify-center flex-grow py-4">
    <div class="text-center">
      <p class="text-white dark:text-black">
        链接打不开，请<a :href="supportLink" target="_blank" class="underline">联系客服</a>。
      </p>
      <p class="text-white dark:text-black">
        Link unavailable, please <a :href="supportLink" target="_blank" class="underline">contact us</a>.
      </p>
    </div>
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
      currentHost: window.location.host
    }
  },
  computed: {
    supportLink() {
      return `https://kefu.${this.currentHost}`
    }
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
