<template>
  <section class="md:pt-6">
    <div class="container flex flex-col items-center py-8 mx-auto sm:flex-row">
      <a
        :href="homeUrl"
        target="_blank"
        class="mt-4 text-sm text-gray-500 sm:ml-4 sm:pl-4 sm:border-l sm:border-gray-200 sm:mt-0"
        title="daifu"
      >
        &copy; {{ new Date().getFullYear() }} All rights reserved
      </a>
    </div>
  </section>
</template>

<script setup>
const homeUrl = '/'
</script>
