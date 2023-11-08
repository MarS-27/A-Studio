<script setup>
import { ref } from "vue"

const activeComment = ref(1);

const clientsFeedbackList = ref([
    {
        id: 1,
        clientName: "Matthew Paul",
        feedback: "Perfect, very good job! Thank you for the amazing design and work. Really impressed with the high quality and quick turnaround time. Highly recommend.",
        photo: "/src/assets/images/matthew_paul.jpeg"
    },
    {
        id: 2,
        clientName: "Sara Stein",
        feedback: "Thank you for the amazing design and work. I recommend this team.",
        photo: "/src/assets/images/sara_stein.jpeg"
    },
    {
        id: 3,
        clientName: "John White",
        feedback: "Outstanding! I'm thrilled with the fantastic design and the promptness of the service. The quality of work is exceptional, and I recommend them.",
        photo: "/src/assets/images/john_white.jpeg"
    },
    {
        id: 4,
        clientName: "Emma Dunn",
        feedback: "I'm absolutely delighted with the superb design and the efficiency of the work. The speed and quality are remarkable. I highly endorse this service.",
        photo: "/src/assets/images/emma_dunn.jpeg"
    },
    {
        id: 5,
        clientName: "Erica Best",
        feedback: "Wow, I couldn't be happier! The design is top-notch, and the quick turnaround is impressive. I'm so impressed with the level of quality and highly recommend their services.",
        photo: "/src/assets/images/erica_best.jpeg"
    },
])

const changeActiveFeedback = (commentId) => {
    activeComment.value = commentId;
}
</script>

<template>
    <section class="grid-content clients-feedback">
        <h3 class="section-title">What our happy client say</h3>
        <p class="section-text">Several selected clients, who already believe in our service.</p>
        <div class="feedback-inner">
            <div>
                <template v-for="clientFeedback in clientsFeedbackList" :key="clientFeedback.id">
                    <div class="feedback-item" v-if="clientFeedback.id === activeComment">
                        <img :src="clientFeedback.photo" :alt="clientFeedback.clientName">
                        <div>
                            <p class="feedback-client-name">{{ clientFeedback.clientName }}</p>
                            <p class="feedback-text">{{ clientFeedback.feedback }}</p>
                            <div class="feedback-buttons">
                                <template v-for="btn in clientsFeedbackList" :key="btn.id">
                                    <button class="feedback-button" :disabled="btn.id === activeComment" type="button"
                                        @click="changeActiveFeedback(btn.id)"></button>
                                </template>
                            </div>
                        </div>
                    </div>
                </template>
            </div>
            <div class="cliens-photos-circle">
                <img class="photo_1" src="/src/assets/images/sara_stein.jpeg" alt="Sara Stein">
                <img class="photo_2" src="/src/assets/images/emma_dunn.jpeg" alt="Emma Dunn">
                <img class="photo_3" src="/src/assets/images/erica_best.jpeg" alt="Erica Best">
                <img class="photo_4" src="/src/assets/images/elly_sun.jpeg" alt="Elly Sun">
                <img class="photo_5" src="/src/assets/images/phil_sommers.jpeg" alt="Phil Sommers">
                <img class="photo_6" src="/src/assets/images/sabrina_himenez.jpeg" alt="Sabrina Himenez">
                <img class="photo_7" src="/src/assets/images/john_white.jpeg" alt="John White">
                <img class="photo_8" src="/src/assets/images/sam_spring.jpeg" alt="Sam Spring">
            </div>
        </div>
    </section>
</template>

<style scoped>
.clients-feedback {
    margin-top: 181px;

    & .section-title {
        text-align: center;
        margin-bottom: 17px;
    }

    & .section-text {
        text-align: center;
        margin-bottom: 113px;
    }

    @media (max-width: 768px) {
        margin-top: 80px;

        & .section-text {
            margin-bottom: 50px;
        }
    }
}

.feedback-inner {
    display: flex;
    justify-content: space-between;
    gap: 10px;
}

.feedback-item {
    display: flex;
    gap: 67px;
    position: relative;

    & img {
        width: 389px;
        min-width: 310px;
        height: 389px;
        object-fit: cover;
        box-shadow: 10px 20px 50px 0px rgba(0, 0, 0, 0.15);
        border-radius: 500px 0px 500px 500px;
    }

    &::after {
        content: '';
        position: absolute;
        bottom: 12px;
        left: -10px;
        z-index: -5;
        width: 120px;
        height: 120px;
        border: 8px solid var(--clr-pink);
        border-radius: 100%;
    }

    &::before {
        content: '';
        position: absolute;
        width: 196px;
        height: 154px;
        top: -42px;
        left: 230px;
        z-index: -5;
        background-image: url('/src/assets/images/Dot.svg');
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
    }

    &>div {
        max-width: 412px;
        margin-top: 84px;
    }


    @media (max-width: 1200px) {
        gap: 20px;
    }

    @media (max-width: 768px) {
        &::before {
            left: 30px;
        }

        &::after {
            bottom: -12px;
        }

        & img {
            width: 240px;
            min-width: 200px;
            height: 240px;
        }

        &>div {
            margin-top: 0;
        }
    }

    @media (max-width: 500px) {

        &::after {
            bottom: 62px;
            width: 60px;
            height: 60px;
            border-width: 4px;
        }

        & img {
            width: 100px;
            min-width: 80px;
            height: 100px;
        }
    }
}

.feedback-client-name {
    font-size: var(--text-xl);
    font-weight: 600;
    margin-bottom: 27px;

    @media (max-width: 768px) {
        font-size: var(--text-m);
        margin-bottom: 15px;
    }
}

.feedback-text {
    color: var(--clr-soft-gray);
    font-size: var(--text-s);
    line-height: 160%;
    margin-bottom: 40px;

    @media (max-width: 768px) {
        font-size: var(--text-xs);
    }
}

.feedback-buttons {
    display: flex;
    align-items: center;
    gap: 26px;
}

.feedback-button {
    width: 16px;
    height: 16px;
    border-radius: 100%;
    background-color: #E7F0FC;
    transition: all;
    transition-duration: 300ms;

    &:hover {
        transform: scale(1.5);
    }

    &:disabled {
        background-color: var(--clr-blue);
        cursor: auto;

        &:hover {
            transform: scale(1);
        }
    }
}

.cliens-photos-circle {
    position: relative;
    max-width: 348px;
    padding: 107px 40px 128px 124px;
    align-self: flex-start;

    & img {
        border-radius: 100%;
        object-fit: cover;
    }

    &::after {
        content: "";
        position: absolute;
        width: 184px;
        height: 184px;
        border-radius: 100%;
        background-color: var(--clr-orange);
        top: 107px;
        left: 21px;
        z-index: -1;
    }

    @media (max-width: 1200px) {
        scale: 0.8;
    }

    @media (max-width: 1024px) {
        scale: 0.7;
    }

    @media (max-width: 920px) {
        position: absolute;
        scale: 0.4;
        top: 120px;
        right: -60px;
    }

    @media (max-width: 768px) {
        display: none;
    }
}

.photo_1 {
    width: 120px;
    height: 120px;

}

.photo_2,
.photo_7 {
    position: absolute;
    width: 98px;
    height: 98px;
}

.photo_3,
.photo_6,
.photo_8 {
    position: absolute;
    width: 68px;
    height: 68px;
}

.photo_4,
.photo_5 {
    position: absolute;
    width: 54px;
    height: 54px;
}

.photo_2 {
    left: 0;
    top: 58px;
}

.photo_3 {
    top: 0;
    left: 137px;
}

.photo_4 {
    top: 63px;
    right: -19px;
}

.photo_5 {
    top: 150px;
    right: -44px;
}

.photo_6 {
    bottom: 60px;
    right: -8px;
}

.photo_7 {
    bottom: 0;
    left: 98px;
}

.photo_8 {
    left: 0;
    bottom: 84px;
}
</style>