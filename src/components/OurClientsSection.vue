<script setup>
</script>

<template>
    <section class="grid-content clients">
        <div class="clients-info">
            <h3 class="section-title">Our Client</h3>
            <p class="section-text">Several selected clients, who already believe in our service.</p>
        </div>
        <div class="clients-images">
            <img src="../assets/images/google-logo.svg" alt="google">
            <img src="../assets/images/airbnb-logo.svg" alt="airbnb">
            <img src="../assets/images/uber-eats-logo.svg" alt="uber-eats">
            <img src="../assets/images/amazon-logo.svg" alt="amazon">
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
}

.clients-info {
    max-width: 320px;

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
}
</style>