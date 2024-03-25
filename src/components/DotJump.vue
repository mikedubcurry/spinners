<script setup>
import Overlay from "./Overlay.vue";
</script>

<template>
  <Overlay>
    <div class="dots">
      <span class="one"></span>
      <span class="two"></span>
      <span class="three"></span>
    </div>
  </Overlay>
</template>
<style scoped>
.dots {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 8px;
  --duration: 1.2s;
}
span {
  width: 15px;
  height: 15px;
  background-color: blue;
  border-radius: 50%;
  animation: bounce var(--duration) ease infinite forwards;
}
.one {
  animation-delay: 0;
}
.two {
  animation-delay: calc(var(--duration) / 3);
}
.three {
  animation-delay: calc(var(--duration) * 2 / 3);
}

@keyframes bounce {
  0% {
    transform: translateY(0)  scale(100%);
  }
  33% {
    transform: translateY(-8px) scale(115%);

  }
  66% {
    transform: translateY(0)  scale(75%);
  }
  100% {
    transform: translateY(0)  scale(100%);
  }
}
</style>
