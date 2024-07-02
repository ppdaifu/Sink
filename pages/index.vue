<template>
  <NuxtLayout name="default">
    <div class="w-full h-full max-w-[600px] mx-auto flex flex-col items-center justify-center text-center">
      <header class="w-full bg-gray-800 text-white p-4">
      </header>
      <main class="flex flex-col items-center justify-center flex-grow py-10">
        <div class="text-white dark:text-black">
          <p>链接打不开，请联系客服。</p>
          <p>Link unavailable, contact support.</p>
        </div>
      </main>
      <footer class="w-full bg-gray-800 text-white p-4">
      </footer>
    </div>
  </NuxtLayout>
</template>

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
</style>
