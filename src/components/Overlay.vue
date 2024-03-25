<template>
  <div class="overlay"><slot /></div>
</template>

<style scoped>
.overlay {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background: rgb(0 0 0 / 50%);
  display: flex;
  justify-content: center;
  align-items: center;
  transition: all 0.3s ease;
}
</style>
