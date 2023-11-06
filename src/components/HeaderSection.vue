<script setup>
import BurgerButton from "./BurgerButton.vue";
import { ref } from "vue"

const navList = ref(['Home', 'What We Do', 'Service', 'Project', 'Blog', 'Contact'])
const isMobileMenuOpen = ref(false)

</script>

<template>
    <header class="grid-container">
        <div class="grid-content header-content">
            <p class="logo"><span class="logo_black">A+ </span>Studio</p>
            <nav class="nav">
                <ul class="nav-list">
                    <li class="nav-item" v-for="item in navList" :key="item">
                        <a href="#" :alt="item">{{ item }}</a>
                    </li>
                </ul>
            </nav>
            <BurgerButton :is-menu-open="isMobileMenuOpen" @toggleburger-button="isMobileMenuOpen = !isMobileMenuOpen" />
            <p>{{ isMobileMenuOpen }}</p>
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

.nav-list {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 60px;

    @media (max-width: 920px) {
        gap: 30px;
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