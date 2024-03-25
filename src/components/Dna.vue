<script setup>
import Overlay from "./Overlay.vue";
</script>

<template>
    <Overlay>
        <div class="dots">
            <template v-for="dot in [1, 2, 3, 4, 5, 6, 7, 8, 9]">
                <span :class="dot" :style="{ '--delay': dot / 2 + 's' }" />
            </template>
        </div>
    </Overlay>
</template>
<style scoped>
.dots {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: flex-start;
    gap: 8px;
    width: 28px;
    --duration: 1.2s;
}

span {
    width: 8px;
    height: 8px;
    background-color: blue;
    border-radius: 50%;
    animation: dna var(--duration) ease-in-out infinite forwards;
    animation-delay: var(--delay);
}

@keyframes dna {
    0% {
        transform: translateX(0);
    }

    50% {
        transform: translateX(28px);
    }

    100% {
        transform: translateX(0%);
    }
}
</style>

