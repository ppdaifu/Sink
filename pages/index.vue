<template>
  <div class="container">
    <p class="text-link">链接无效</p>
  </div>
</template>

<script>
export default {
}
</script>

<style scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh; /* Full viewport height */
  margin: 0; /* No margin */
}

.text-link {
  color: black; /* Default text color */
}

.dark .text-link {
  color: white; /* Text color for dark mode */
}

html, body {
  height: 100%; /* Ensure the body takes the full height */
  margin: 0; /* Remove default margin */
}
</style>
