<template>
  <div class="flex flex-col min-h-screen justify-center items-center">
    <main class="flex flex-col justify-center items-center flex-grow text-center">
      <!-- 显示一句话提示语 -->
      <p class="text-link">链接无效</p>
    </main>
  </div>
</template>

<script>
export default {
}
</script>

<style scoped>
.text-link {
  color: black; /* Default text color for light mode */
}
.dark .text-link {
  color: white; /* Text color for dark mode */
}
.min-h-screen {
  min-height: 100vh; 
}
.flex {
  display: flex;
}
.flex-col {
  flex-direction: column;
}
.justify-center {
  justify-content: center;
}
.items-center {
  align-items: center;
}
.flex-grow {
  flex-grow: 1;
}
.text-center {
  text-align: center;
}
html, body {
  height: 100%; /* Ensure the body takes the full height */
  margin: 0; /* Remove default margin */
}
</style>
