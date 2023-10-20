<script setup>
import MainButton from './MainButton.vue';


</script>

<template>
    <section class="grid-content intro">
        <div class="intro-info">
            <h1 class="intro-title">A Digital Product Agency</h1>
            <p class="intro-text">Leading digital agency with solid design and development expertise. We build readymade
                websites, mobile
                applications, and elaborate online business services.
            </p>
            <MainButton />
            <div class="intro-dots">
                <img src="../assets/images/Dot.svg" alt="dots">
                <img src="../assets/images/Dot.svg" alt="dots">
            </div>
            <div>
                <img src="../assets/images/intro.png" alt="intro-img">
            </div>
        </div>
    </section>
</template>

<style scoped>
.intro {
    /* min-height: calc(100vh - 118px); */
}

.intro-info {
    position: relative;
    padding-top: 123px;
    max-width: 471px;
}

.intro-title {
    font-size: var(--text-3xl);
    font-weight: 900;
    margin-bottom: 40px;
}

.intro-text {
    color: var(--clr-gray);
    line-height: 160%;
    font-size: var(--text-s);
    margin-bottom: 33px;
}

.intro-dots {
    display: flex;
    gap: 12px;
    position: absolute;
    left: -53px;
    top: calc(100% - 35px);
    z-index: -1;
}
</style>