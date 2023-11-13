<script setup>
import MainButton from './MainButton.vue';

import { ref } from "vue"

const btnVariant = ref("small");

const enteredEmail = ref('');

const submitForm = (e) => {
    e.preventDefault();
    if (enteredEmail.value) {
        alert(`The entered email address ${enteredEmail.value} has been sent!`);
        enteredEmail.value = '';
    } else {
        alert(`Enter email address, please!`);
    }
}
</script>

<template>
    <section class="grid-content contact">
        <div class="contact-info">
            <h3 class="section-title">Subscribe Newsletter</h3>
            <p class="section-text">I will update good news and promotion service not spam</p>
        </div>
        <form class="contact-form" @submit="submitForm">
            <input v-model="enteredEmail" class="contact-input" type="email" placeholder="Enter your email address.." />
            <div>
                <MainButton :variant="btnVariant" />
            </div>
        </form>
    </section>
</template>

<style scoped>
.contact {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 20px;
    position: relative;
    margin-top: 148px;
    margin-bottom: 146px;
    border-radius: 75px;
    background-color: #F4F9FF;
    background-image: url("/assets/images/contact-rectangle.svg");
    background-position: right;
    background-repeat: no-repeat;
    padding: 98px 98px 99px 92px;

    &::before {
        content: '';
        display: block;
        position: absolute;
        z-index: -1;
        left: -38px;
        bottom: -39px;
        width: 178px;
        height: 178px;
        border-bottom-left-radius: 100px;
        background-color: var(--clr-orange);
    }

    &::after {
        content: '';
        position: absolute;
        width: 175px;
        height: 154px;
        top: -56px;
        right: -37px;
        z-index: -1;
        background-image: url('/assets/images/Dot.svg');
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
    }

    @media (max-width: 860px) {
        padding-right: 40px;
        padding-left: 40px;
    }

    @media (max-width: 768px) {
        flex-direction: column;
        gap: 60px;
        text-align: center;
        padding-top: 40px;
        background-position: bottom 40px right 50%;
        background-size: 280px 160px;
        margin-top: 60px;
        margin-bottom: 60px;

        &::after {
            top: -36px;
        }
    }
}

.contact-info {
    & .section-title {
        margin-bottom: 17px;
    }
}

.contact-form {
    position: relative;
    max-width: 577px;

    & div {
        position: absolute;
        top: 50%;
        translate: 0 -50%;
        right: 10px;
    }

    @media (max-width: 768px) {
        & div {
            right: 5px;
        }
    }
}

.contact-input {
    width: 479px;
    height: 80px;
    padding: 10px 210px 10px 34px;
    border-radius: 60px;
    border: 1px solid #F1F1F1;
    background: var(--clr-white);
    box-shadow: 10px 20px 50px 0px rgba(0, 0, 0, 0.15);
    font-family: 'Averta-Regular';
    font-size: var(--text-l);

    &::placeholder {
        color: #959595;
        font-size: var(--text-s);
    }

    @media (max-width: 860px) {
        width: 440px;
        padding-left: 20px;
    }

    @media (max-width: 768px) {
        width: 300px;
        height: 50px;
        padding: 5px 150px 5px 10px;
        font-size: var(--text-s);

        &::placeholder {
            font-size: var(--text-xs);
        }
    }
}
</style>