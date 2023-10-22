<script setup>
import MainButton from './MainButton.vue';
</script>

<template>
    <section class="grid-content intro">
        <div class="intro-info">
            <h1 class="section-title">A Digital Product Agency</h1>
            <p class="section-text">Leading digital agency with solid design and development expertise. We build readymade
                websites, mobile
                applications, and elaborate online business services.
            </p>
            <MainButton />
            <div class="intro-dots">
                <img src="../assets/images/Dot.svg" alt="dots">
                <img src="../assets/images/Dot.svg" alt="dots">
            </div>
        </div>
        <div class="intro-img">
            <img src="../assets/images/intro.png" alt="intro-img">
        </div>
    </section>
</template>

<style scoped>
.intro {
    position: relative;
}

.intro-info {
    position: relative;
    padding-top: 123px;
    max-width: 471px;

    & .section-title {
        margin-bottom: 40px;
    }

    & .section-text {
        margin-bottom: 33px;
    }
}

.intro-dots {
    display: flex;
    gap: 12px;
    position: absolute;
    left: -53px;
    top: calc(100% - 35px);
    z-index: -1;
}

.intro-img {
    position: absolute;
    max-width: 754px;
    width: 63%;
    height: 512px;
    top: 0;
    right: -120px;

    & img {
        width: 100%;
        height: 100%;
        border-bottom-left-radius: 200px;
        object-fit: cover;
    }

    &::before {
        content: '';
        display: block;
        position: absolute;
        left: -63px;
        width: 129px;
        height: 129px;
        border-radius: 100%;
        background-color: #DAE9FF;
    }

    &::after {
        content: '';
        display: block;
        position: absolute;
        z-index: -1;
        right: 120px;
        bottom: -96px;
        width: 178px;
        height: 178px;
        border-bottom-right-radius: 100px;
        background-color: var(--clr-orange);
    }

    /* @media (max-width: 1200px) {
    } */

}
</style>