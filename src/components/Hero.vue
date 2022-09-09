<script setup>
import Button from "@/components/Button.vue";
</script>

<template>
    <section class="position-relative">
        <div class="container-xl">
            <div class="row align-items-center flex-lg-row flex-column-reverse">
                <div class="col-lg-6">
                    <h1 class="title">A Simple Bookmark Manager</h1>
                    <p class="description">
                        A clean and simple interface to organize your favourite websites. Open a new browser tab and see
                        your sites load instantly. Try it for free.
                    </p>
                    <div class="cta-container">
                        <Button href="#" class="button-blue">Get it on Chrome</Button>
                        <Button href="#" class="button-gray">Get it on Firefox</Button>
                    </div>
                </div>
                <div class="col-lg-6">
                    <img class="hero-banner" src="@/assets/images/illustration-hero.svg" alt="" />
                    <div class="hero-bg"></div>
                </div>
            </div>
        </div>
    </section>
</template>
<script>
export default {};
</script>
<style lang="scss" scoped>
section {
    margin: 6rem auto;
}
.hero-banner {
    display: block;
    margin-left: auto;
    position: relative;
    right: -4rem;
    top: 0;
    width: 100%;
}
.hero-bg {
    aspect-ratio: 3/2;
    max-height: 370px;
    width: 35%;
    background-color: var(--clr-blue);
    position: absolute;
    right: 0;
    bottom: -2rem;
    z-index: -1;
    border-radius: 0 0 0 10rem;
}
.title {
    font-size: clamp(2rem, calc(1.5vw + 2rem), 3.5rem);
    line-height: 1;
    margin-bottom: 2rem;
}
.description {
    color: var(--clr-gray);
    font-size: 1.25rem;
    max-width: 90%;
    margin-bottom: 2rem;
}
.cta-container {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    gap: 0.5rem 1rem;
}
@media (max-width: 1199px) {
    .hero-banner {
        display: block;
        margin-left: auto;
        position: relative;
        right: 0rem;
        top: 0;
        width: 100%;
    }
}
@media (max-width: 991px) {
    .hero-banner {
        display: block;
        margin: auto;
        width: min(475px, 100%);
    }
    .col-lg-6 {
        position: relative;
        text-align: center;
    }
    .hero-bg {
        aspect-ratio: 4.5/3;
        max-height: 275px;
        width: 60%;
    }
    .title {
        margin-top: 7rem;
    }
    .description {
        margin: 0 auto 2rem;
    }
    .cta-container {
        justify-content: center;
    }
}
@media (max-width: 575px) {
    .hero-bg {
        width: 85%;
        border-radius: 0 0 0 8rem;
    }
}
</style>
