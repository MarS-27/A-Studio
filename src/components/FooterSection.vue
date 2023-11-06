<script setup>
import { ref } from "vue"

const footerLinks = ref([
    {
        title: "What We Do",
        links: ["Web Design ", "App Design", "Social Media Manage", "Market Analysis Project"]
    },
    {
        title: "Company",
        links: ["About Us", "Career", "Become Investor"]
    },
    {
        title: "Support",
        links: ["FAQ", "Policy", "Business"]
    },
    {
        title: "Contact",
        links: ["WhatsApp", "Support 24"]
    }
])
</script>

<template>
    <footer class="grid-container">
        <div class="grid-content footer-content">
            <div class="footer-info">
                <p class="logo"><span class="logo_black">A+ </span>Studio</p>
                <p class="footer-text">Leading digital agency with solid design and development expertise. We build
                    readymade websites, mobile applications, and elaborate online business services.
                </p>
            </div>
            <div class="footer-links">
                <div v-for="item in footerLinks" :key="item.title">
                    <p class="footer-links-title">{{ item.title }}</p>
                    <ul>
                        <li class="footer-link" v-for="link in item.links" :key="link">
                            <a href="#">{{ link }}</a>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
        <div class="grid-content social-links">
            <a href="https://www.facebook.com" target="_blank">
                <img src="/src/assets/icons/facebook.svg" alt="facebook">
            </a>
            <a href="https://twitter.com" target="_blank">
                <img src="/src/assets/icons/twitter.svg" alt="twitter">
            </a>
            <a href="https://www.linkedin.com" target="_blank">
                <img src="/src/assets/icons/linkedin.svg" alt="linkedin">
            </a>
        </div>
        <p class="grid-content copyright">
            Copyright © 2022
        </p>
    </footer>
</template>

<style scoped>
.footer-content {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    gap: 40px;
    padding-top: 60px;
    border-top: 1px solid #E4E4E4;
    margin-bottom: 20px;
}

.footer-info {
    max-width: 270px;
}

.logo {
    font-size: var(--text-xl);
    margin-bottom: 26px;
}

.logo_black {
    font-weight: 900;
}

.footer-text {
    color: var(--clr-gray);
    font-size: var(--text-xs);
    line-height: 160%;
}

.footer-links {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    flex-grow: 1;
    gap: 20px;
    max-width: 740px;
}

.footer-links-title {
    font-size: vab(--text-xl);
    font-weight: 900;
    margin-bottom: 24px;
}

.footer-link {
    font-size: var(--text-xs);
    line-height: 200%;

    & a::after {
        content: '';
        display: block;
        position: absolute;
        top: 100%;
        width: 0;
        height: 1.5px;
        background-color: var(--clr-gray);
        transition: all 350ms ease-in-out;
    }

    & a:hover::after {
        width: 100%;
    }
}

.social-links {
    display: flex;
    align-items: center;
    justify-content: flex-start;
    gap: 16px;
    margin-bottom: 29px;

    & a {
        display: block;
        width: 36px;
        height: 36px;
        border-radius: 100%;
        transition: all;
        transition-duration: 300ms;

        &:hover {
            transform: scale(1.3);
        }
    }
}

.copyright {
    color: #A4A4A4;
    font-family: Averta Demo PE Cutted Demo;
    font-size: var(--text-xs);
    line-height: 160%;
    text-align: center;
    padding: 17px 0 23px 0;
    border-top: 1px solid #F1F1F1;
}
</style>