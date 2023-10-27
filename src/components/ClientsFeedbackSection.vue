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
            <div class="feedback-list">
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
                <img src="" alt="">
                <img src="" alt="">
                <img src="" alt="">
                <img src="" alt="">
                <img src="" alt="">
                <img src="" alt="">
                <img src="" alt="">
                <img src="" alt="">
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
}

.feedback-inner {}

.feedback-list {}

.feedback-item {
    display: flex;
    gap: 20px;
    position: relative;

    & img {
        width: 389px;
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

    &>div {
        max-width: 412px;
        margin-top: 84px;
    }
}

.feedback-client-name {
    margin-bottom: 21px;
    font-size: var(--text-xl);
    font-weight: 600;
    margin-bottom: 27px;
}

.feedback-text {
    color: var(--clr-soft-gray);
    font-size: var(--text-s);
    line-height: 160%;
    margin-bottom: 40px;
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
</style>