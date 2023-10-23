<script setup>
</script>

<template>
    <section class="grid-content video-guide">
        <div class="video-guide-content">
            <video src="../assets/video/DigitalAgency.mp4"></video>
            <button type="button" class="video-play-button">
                <img src="../assets/icons/play-icon.svg" alt="play">
            </button>
        </div>
        <div class="video-guide-info">
            <h3 class="section-title">Great Digital Product Agency since 2016 </h3>
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
}

.video-guide-content {
    position: relative;
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
}

.video-play-button {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 78px;
    height: 78px;
    background-color: var(--clr-blue);
    border-radius: 100%;
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