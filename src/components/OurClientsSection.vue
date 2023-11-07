<script setup>
</script>

<template>
    <section class="grid-content clients">
        <div class="clients-info">
            <h3 class="section-title">Our Clients</h3>
            <p class="section-text">Several selected clients, who already believe in our service.</p>
        </div>
        <div class="clients-images">
            <img src="/src/assets/images/google-logo.svg" alt="google">
            <img src="/src/assets/images/airbnb-logo.svg" alt="airbnb">
            <img src="/src/assets/images/uber-eats-logo.svg" alt="uber-eats">
            <img src="/src/assets/images/amazon-logo.svg" alt="amazon">
        </div>
    </section>
</template>

<style scoped>
.clients {
    margin-top: 260px;
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    gap: 10px;

    @media (max-width: 1024px) {
        flex-direction: column;
        align-items: center;
    }

    @media (max-width: 768px) {
        margin-top: 180px;
    }
}

.clients-info {
    max-width: 320px;

    @media (max-width: 1024px) {
        text-align: center;
    }

    & .section-title {
        margin-bottom: 17px
    }
}

.clients-images {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 20px;
    flex-grow: 1;
    margin-bottom: 10px;

    @media (max-width: 1024px) {
        width: 100%;
    }

    @media (max-width: 768px) {
        display: grid;
        grid-template-columns: repeat(2, 1fr);

        & img {
            width: 120px;
            height: 30px;
            margin: 0 auto;
        }
    }
}
</style>