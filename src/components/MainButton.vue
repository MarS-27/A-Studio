<script setup>
defineProps({
    variant: String,
})
</script>

<template>
    <button class="main-button" :class="variant">
        Contact Now
    </button>
</template>

<style scoped>
.main-button {
    padding: 20px 40px;
    border-radius: 60px;
    background-color: var(--clr-blue);
    color: var(--clr-white);
    font-family: "Averta-Regular";
    transition: filter;
    transition-duration: 300ms;

    &:hover {
        filter: drop-shadow(2px 4px 6px var(--clr-gray));
    }
}

.small {
    font-size: var(--text-s);
    letter-spacing: 1.04px;
}

.medium {
    font-size: var(--text-l);
    letter-spacing: 1.3px;
}
</style>