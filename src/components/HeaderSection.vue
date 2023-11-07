<script setup>
import BurgerButton from "./BurgerButton.vue";
import { ref, onMounted } from "vue"

const navList = ref(['Home', 'What We Do', 'Service', 'Project', 'Blog', 'Contact'])
const isMobileMenuOpen = ref(false)

onMounted(() => {
    window.addEventListener('resize', closeMobileMenuIfLargeScreen)
})

const closeMobileMenuIfLargeScreen = () => {
    if (window.innerWidth > 768) {
        isMobileMenuOpen.value = false
    }
}
</script>

<template>
    <header class="grid-container">
        <div class="grid-content header-content">
            <p class="logo"><span class="logo_black">A+ </span>Studio</p>
            <nav class="nav" :class="isMobileMenuOpen ? 'nav-mobile' : null">
                <ul class="nav-list">
                    <li class="nav-item" v-for="item in navList" :key="item">
                        <a href="#" :alt="item" @click="isMobileMenuOpen = false">{{ item }}</a>
                    </li>
                </ul>
            </nav>
            <BurgerButton :is-menu-open="isMobileMenuOpen" @toggle-burger-button="isMobileMenuOpen = !isMobileMenuOpen" />
        </div>
    </header>
</template>

<style scoped>
.header-content {
    padding: 42px 0 40px 0;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 10px;

    @media (max-width: 768px) {
        padding: 20px 0;
    }
}

.logo {
    font-size: var(--text-2xl);
    min-width: 121px
}

.logo_black {
    font-weight: 900;
}

.nav {
    font-size: var(--text-s);
    letter-spacing: 0.16px;

    @media (max-width: 768px) {
        display: none;
    }
}

.nav-mobile {
    display: block;
    width: 50%;
    z-index: 10;
    position: absolute;
    padding: 20px;
    right: 0;
    top: 80%;
    background-color: var(--clr-main-bg);
    border: 1px solid #E4E4E4;
    border-radius: 8px;
}

.nav-list {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 60px;

    @media (max-width: 920px) {
        gap: 30px;
    }

    @media (max-width: 768px) {
        flex-direction: column;
        gap: 20px;
    }
}

.nav-item {
    position: relative;

    & a {
        font-weight: 600;
    }

    &::after {
        content: '';
        display: block;
        position: absolute;
        top: 100%;
        width: 0;
        height: 2px;
        background-color: var(--clr-black);
        transition: all 350ms ease-in-out;
    }

    &:hover::after {
        width: 100%;
    }
}
</style>