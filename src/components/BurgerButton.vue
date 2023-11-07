<script setup>
defineProps({
    isMenuOpen: Boolean,
})

</script>

<template>
    <button class="burger-btn" :class="isMenuOpen ? 'mobile-menu-open' : null" @click="$emit('toggle-burger-button')">
        <div></div>
        <div></div>
        <div></div>
    </button>
</template>

<style scoped>
.burger-btn {
    display: none;
    flex-direction: column;
    justify-content: space-between;
    gap: 4px;
    width: 40px;
    min-width: 40px;
    padding: 4px;
    display: none;
    background-color: inherit;

    & div {
        width: 100%;
        height: 4px;
        background-color: var(--clr-gray);
        transition: all;
        transition-duration: 300ms;
    }

    @media (max-width: 768px) {
        display: flex;
    }
}


.mobile-menu-open {

    & div:first-of-type {
        rotate: 45deg;
        translate: 0 8px;
    }

    & div:nth-child(2n) {
        translate: -40px 0;
        background-color: transparent;
        pointer-events: none;

    }


    & div:last-of-type {
        rotate: -45deg;
        translate: 0 -8px;
    }
}
</style>