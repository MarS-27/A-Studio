<script setup>
import { ref } from "vue"

const navList = ref(['Home', 'What We Do', 'Service', 'Project', 'Blog', 'Contact'])
</script>

<template>
    <header class="grid-container">
        <div class="grid-content header-content">
            <p class="logo"><span class="logo_black">A+ </span>Studio</p>
            <nav class="nav">
                <ul class="nav-list">
                    <li class="nav-item" v-for="item in navList" :key="item">
                        <a>{{ item }}</a>
                    </li>
                </ul>
            </nav>
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
    font-weight: 600;
    letter-spacing: 0.16px;
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

.nav-item {}
</style>