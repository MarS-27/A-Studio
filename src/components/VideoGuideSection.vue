<script setup>
import { ref } from 'vue';

const isVideoPlay = ref(false);

const video = ref(null)

const togggleVideoPlay = () => {
    isVideoPlay.value = !isVideoPlay.value;

    if (isVideoPlay.value) {
        video.value.play();
    }
};
</script>

<template>
    <section class="grid-content video-guide">
        <div class="video-guide-content">
            <video ref="video" src="/assets/video/DigitalAgency.mp4" @pause="togggleVideoPlay"
                poster="/assets/images/video-preload-img.png" :controls="isVideoPlay"></video>
            <button type="button" class="video-play-button" @click="togggleVideoPlay" v-if="!isVideoPlay">
                <img src="/assets/icons/play-icon.svg" alt="play">
            </button>
        </div>
        <div class="video-guide-info">
            <h3 class="section-title">Great Digital Product Agency since 2016</h3>
            <p class="section-text">Our Business Plan is a written document describing a company's core business activites,
                Objectives, and how it plans to achieve its goals. Our goal is to provide our client high quality Product
                with modern idea accordingly their budgets and according thir reuirements.
            </p>
        </div>
    </section>
</template>

<style scoped>
.video-guide {
    margin-top: 225px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 20px;


    @media (max-width: 768px) {
        flex-direction: column-reverse;
        margin-top: 120px;
        text-align: center;
    }

    @media (max-width: 420px) {
        margin-top: 80px;
    }
}

.video-guide-content {
    position: relative;
    min-width: 350px;
    max-width: 550px;
    height: 372px;
    border-radius: 32px;
    box-shadow: 10px 20px 50px 0px rgba(0, 0, 0, 0.15);

    & video {
        width: 100%;
        height: 100%;
        object-fit: cover;
        border-radius: 32px;
    }

    &::after {
        content: '';
        display: block;
        position: absolute;
        z-index: -1;
        right: -41px;
        bottom: -60px;
        width: 129px;
        height: 129px;
        border-radius: 100%;
        background-color: var(--clr-orange);
    }

    @media (max-width: 768px) {
        min-width: 320px;
        height: 250px;
    }
}

.video-play-button {
    display: flex;
    align-items: center;
    justify-content: center;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 78px;
    height: 78px;
    background-color: var(--clr-blue);
    border-radius: 100%;
    transition: filter;
    transition-duration: 300ms;

    &:hover {
        filter: drop-shadow(2px 4px 6px var(--clr-gray));
    }

    & img {
        width: 36px;
        height: 40px;
        margin-left: 5px;
    }

    @media (max-width: 768px) {
        width: 48px;
        height: 48px;

        & img {
            width: 16px;
            height: 20px;
            margin-left: 3px;
        }
    }
}

.video-guide-info {
    max-width: 532px;

    & .section-title {
        position: relative;
        margin-bottom: 30px;

        &::before {
            content: '';
            display: block;
            position: absolute;
            z-index: -10;
            left: -39px;
            top: -18px;
            width: 178px;
            height: 178px;
            border-bottom-right-radius: 100px;
            background-color: #EFF1FF;
        }
    }
}
</style>