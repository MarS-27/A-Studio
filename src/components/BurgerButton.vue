<script setup>

// import { ref } from "vue"

defineProps({
    isMenuOpen: Boolean,
})

</script>

<template>
    <button class="burger-btn" @click="$emit('toggleburger-button')">
        <div class="burger-line"></div>
    </button>
</template>

<style scoped>
.burger-btn {
    width: 40px;
    min-width: 40px;
    padding: 4px;
    display: none;
    background-color: inherit;

    @media (max-width: 768px) {
        display: block;
    }
}

.burger-line {
    position: relative;
    width: 100%;
    height: 4px;
    background-color: var(--clr-gray);
    transition: all;
    transition-duration: 300ms;

    &::before,
    &::after {
        content: "";
        position: absolute;
        left: 0;
        width: 100%;
        height: 4px;
        background-color: var(--clr-gray);
        transition: all;
        transition-duration: 300ms;
    }

    &::before {
        top: -8px;
    }

    &::after {
        bottom: -8px;
    }

}
</style>