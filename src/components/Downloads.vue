<script setup>
import Button from "@/components/Button.vue";
import { chrome, opera, firefox } from "@/assets/images";
</script>

<script>
export default {
    data() {
        return {
            platforms: [
                {
                    image: chrome,
                    title: "Add to Chrome",
                    description: "Minimum version 62",
                    link: { text: "Add & Install Extension", url: "#" },
                },
                {
                    image: firefox,
                    title: "Add to Firefox",
                    description: "Minimum version 55",
                    link: { text: "Add & Install Extension", url: "#" },
                },
                {
                    image: opera,
                    title: "Add to Opera",
                    description: "Minimum version 46",
                    link: { text: "Add & Install Extension", url: "#" },
                },
            ],
        };
    },
};
</script>

<template>
    <section>
        <div class="container-xl">
            <h2 class="section-title text-center">Download the extension</h2>
            <p class="section-subtitle text-center">
                We've got more browsers in the pipeline. Please do let us know if you've got a favourite you'd like us
                to prioritize.
            </p>
            <div class="download-row">
                <div class="download-item" v-for="(platform, index) in platforms" :key="index">
                    <div class="p-4">
                        <img class="download-image" :src="platform.image" :alt="platform.title" />
                        <h4 class="download-title">{{ platform.title }}</h4>
                        <p class="download-subtitle">{{ platform.description }}</p>
                    </div>
                    <img src="@/assets/images/bg-dots.svg" class="img-fluid w-100" alt="" />
                    <div class="p-4">
                        <Button href="#" class="button-blue w-100">Add & Install Extension</Button>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
section {
    margin: 12rem auto 6rem;
}
.section-title {
    font-size: clamp(1.75rem, calc(1.25vw + 1.5rem), 2.25rem);
    margin-bottom: 1.5rem;
}
.section-subtitle {
    color: var(--clr-gray);
    font-size: 1.25rem;
    width: min(100%, 600px);
    margin: 0 auto 3.5rem;
}
.download-row {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 2rem;
    align-items: flex-start;
    .download {
        &-image {
            margin-bottom: 2.5rem;
        }
        &-item {
            border-radius: 1rem;
            box-shadow: 0 8px 10px 0px hsla(231, 69%, 60%, 10%);
            text-align: center;
            &:nth-child(2) {
                margin-top: 2.5rem;
            }
            &:nth-child(3) {
                margin-top: 5rem;
            }
        }
        &-subtitle {
            font-size: 1rem;
            color: var(--clr-gray);
            margin-bottom: 0;
        }
    }
}
@media (max-width: 991px) {
    .download-row {
        flex-direction: column;
        align-items: center;
        .download {
            &-item {
                margin-top: 0 !important;
            }
        }
    }
}
</style>
