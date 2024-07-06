<template>
  <main class="flex flex-col min-h-screen">
    <LayoutsHeader />
    <section class="flex flex-1">
      <div class="container mx-auto">
        <slot />
      </div>
    </section>
    <LayoutsFooter />
  </main>
</template>

<script>
export default {
  head() {
    return {
      script: [
        {
          src: "https://hm.baidu.com/hm.js?7af9cc781ae0b1d55a016f7ae0dde530",
          async: true
        }
      ]
    };
  }
};
</script>
