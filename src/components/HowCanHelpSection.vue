<script setup>
</script>

<template>
    <section class="grid-content can-help">
        <div class="can-help-info">
            <h3 class="section-title">How can we help your Business ?</h3>
            <p class="section-text">We build readymade websites, mobile applications, and elaborate online business
                services.
            </p>
            <div class="can-help-dots">
                <img src="/src/assets/images/Dot.svg" alt="dots">
                <img src="/src/assets/images/Dot.svg" alt="dots">
            </div>
        </div>
        <div class="can-help-cards">
            <div class="card">
                <div class="card-img box-search">
                    <img src="/src/assets/images/box-search.svg" alt="box-search">
                </div>
                <p class="card-title">Financial Planning System</p>
                <p class="card-text">Protocols apart from aengage models, pricing billing</p>
            </div>
            <div class="card">
                <div class="card-img empty-wallet">
                    <img src="/src/assets/images/empty-wallet.svg" alt="empty-wallet">
                </div>
                <p class="card-title">Business Idea Planning</p>
                <p class="card-text">We present you a proposal and discuss niffty-gritty like</p>
            </div>
            <div class="card">
                <div class="card-img code">
                    <img src="/src/assets/images/code.svg" alt="code">
                </div>
                <p class="card-title">Development Website and App</p>
                <p class="card-text">Communication protocols apart from engagement models</p>
            </div>
            <div class="card">
                <div class="card-img chart-square">
                    <img src="/src/assets/images/chart-square.svg" alt="chart-square">
                </div>
                <p class="card-title">Market Analysis Project</p>
                <p class="card-text">Protocols apart from aengage models, pricing billing</p>
            </div>
        </div>
    </section>
</template>

<style scoped>
.can-help {
    display: flex;
    align-items: flex-end;
    position: relative;
    gap: 10px;
    margin-top: 94px;

    &::after {
        content: '';
        position: absolute;
        top: 140px;
        right: -120px;
        z-index: -1;
        width: 87.3%;
        height: 635px;
        background: #F4F9FF;
        border-top-left-radius: 150px;
    }

    @media (max-width: 1024px) {
        flex-direction: column;
        align-items: center;
        text-align: center;
    }

    @media (max-width: 768px) {
        &::after {
            height: 450px;
        }
    }
}

.can-help-info {
    max-width: 396px;

    & .section-title {
        position: relative;
        margin-bottom: 30px;

        &::before {
            content: '';
            display: block;
            position: absolute;
            z-index: -1;
            left: -39px;
            top: -55px;
            width: 178px;
            height: 178px;
            border-top-left-radius: 100px;
            background-color: var(--clr-orange);
        }
    }
}

.can-help-dots {
    display: flex;
    gap: 12px;
    z-index: -5;
    margin-left: 5px;
    margin-top: 104px;

    @media (max-width: 1024px) {
        position: absolute;
        bottom: 0;
        left: 100%;
    }
}

.can-help-cards {
    display: grid;
    position: relative;
    grid-template-columns: repeat(2, 1fr);
    gap: 30px;
    margin: 0 auto;

    &::after {
        content: '';
        position: absolute;
        bottom: -40px;
        right: -40px;
        z-index: -5;
        width: 120px;
        height: 120px;
        border: 8px solid var(--clr-pink);
        border-radius: 100%;
    }

    @media (max-width: 768px) {
        gap: 10px;
    }
}

.card {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    max-width: 308px;
    border-radius: 40px;
    border: 1px solid #F2F2F2;
    background-color: var(--clr-white);
    box-shadow: 0px 10px 50px 0px rgba(0, 0, 0, 0.05);
    padding: 39px 32px 57px 31px;

    &:has(.box-search),
    &:has(.code) {
        transform: translateY(79px);
    }

    @media (max-width: 768px) {
        padding: 20px;
    }
}

.card-img {
    border-radius: 20px;
    padding: 24px;
    margin-bottom: 31px;

    @media (max-width: 768px) {
        padding: 14px;
        margin-bottom: 20px;
    }
}

.box-search {
    background-color: #F1F7FF;
}

.empty-wallet {
    background-color: #FFF7E3;
}

.code {
    background-color: #FFF2F8;
}

.chart-square {
    background-color: #DEFFEE;
}

.card-title {
    text-align: center;
    font-size: var(--text-xl);
    font-weight: 600;
    margin-bottom: 27px;

    @media (max-width: 768px) {
        font-size: var(--text-m);
        margin-bottom: 17px;
    }
}

.card-text {
    color: var(--clr-soft-gray);
    text-align: center;
    font-size: var(--text-s);
    line-height: 140%;

    @media (max-width: 768px) {
        font-size: var(--text-xs);
    }
}
</style>