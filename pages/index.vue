<template>
  <div class="container">
    <main class="content">
      <img src="/assets/images/404.svg" alt="404 Image" class="image" />
      <div class="text-link">
        <p>链接无效，请<a :href="supportLink" target="_blank" class="underline">联系客服</a>。</p>
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
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  width: 100vw;
  overflow: auto;
}

.content {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.image {
  width: 50%;
}

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

.underline {
  text-decoration: underline;
}
</style>
