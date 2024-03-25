<script setup>
import Overlay from "./Overlay.vue";
</script>

<template>
  <Overlay>
      <div class="spinner"></div>
  </Overlay>
</template>

<style scoped>
.spinner {
  width: 80px;
  height: 80px;
  border-bottom: 4px solid blue;
  border-right: 4px solid blue;
  border-radius: 50%;
  animation: .75s spin infinite linear;
}

@keyframes spin {
  to {
    transform: rotate(360deg);
  }
}
</style>
