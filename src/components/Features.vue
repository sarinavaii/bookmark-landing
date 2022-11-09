<script setup>
import Button from "@/components/Button.vue";
import { tabImage1, tabImage2, tabImage3 } from "@/assets/images";
</script>

<script>
export default {
    data() {
        return {
            features: [
                {
                    name: "Simple Bookmarking",
                    title: "Bookmark in one click",
                    image: tabImage1,
                    description:
                        "Organize your bookmarks however you like. Our simple drag-and-drop interface gives you complete control over how you manage your favourite sites.",
                    link: { text: "More Info", url: "#" },
                },
                {
                    name: "Speedy Searching",
                    image: tabImage2,
                    title: "Intelligent search",
                    description:
                        "Our powerful search feature will help you find saved sites in no time at all. No need to trawl through all of your bookmarks.",
                    link: { text: "More Info", url: "#" },
                },
                {
                    name: "Easy Sharing",
                    image: tabImage3,
                    title: "Share your bookmarks",
                    description:
                        "Easily share your bookmarks and collections with others. Create a shareable link that you can send at the click of a button.",
                    link: { text: "More Info", url: "#" },
                },
            ],
        };
    },
};
</script>

<template>
    <section class="position-relative">
        <div class="container-xl">
            <h2 class="section-title text-center">Features</h2>
            <p class="section-subtitle text-center">
                Our aim is to make it quick and easy for you to access your favourite websites. Your bookmarks sync
                between your devices so you can access them on the go.
            </p>
            <ul class="nav flex-lg-row flex-column">
                <li v-for="(feature, index) in features" :key="index" class="nav-item">
                    <button
                        :class="[`nav-link ${index == 0 ? 'active' : ''}`]"
                        data-bs-toggle="pill"
                        :data-bs-target="[`#tab-${index}`]"
                    >
                        {{ feature.name }}
                    </button>
                </li>
            </ul>
            <div class="tab-content" id="pills-tabContent">
                <div
                    v-for="(feature, index) in features"
                    :key="index"
                    :class="[`tab-pane fade ${index == 0 ? 'active show' : ''}`]"
                    :id="[`tab-${index}`]"
                >
                    <div class="row align-items-center justify-content-between">
                        <div class="col-lg-6">
                            <img class="hero-banner" :src="feature.image" :alt="feature.title" />
                            <div class="hero-bg"></div>
                        </div>
                        <div class="col-lg-5">
                            <h3 class="title">{{ feature.title }}</h3>
                            <p class="description">
                                {{ feature.description }}
                            </p>
                            <div class="cta-container">
                                <Button :href="feature.link.url" class="button-blue">
                                    {{ feature.link.text }}
                                </Button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
section {
    margin: 6rem auto;
}
.hero-banner {
    width: 100%;
    aspect-ratio: 1.5;
    object-fit: contain;
    object-position: right;
}
.hero-bg {
    aspect-ratio: 3/2;
    max-height: 370px;
    width: 45%;
    background-color: var(--clr-blue);
    position: absolute;
    left: 0;
    bottom: -4rem;
    z-index: -1;
    border-radius: 0 0 10rem 0;
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
.nav {
    width: min(700px, 100%);
    margin: 3rem auto;
    .nav-item {
        flex-basis: 33%;
        flex-grow: 1;
        border-bottom: 1px solid var(--clr-medium-gray);
    }
    .nav-link {
        border: none;
        color: var(--clr-gray);
        width: 100%;
        background-color: var(--clr-white);
        padding: 1rem;
        position: relative;
        &::after {
            content: "";
            position: absolute;
            bottom: 1px;
            left: 0;
            right: 0;
            margin: auto;
            width: 0;
            height: 3px;
            background-color: var(--clr-red);
            transition: all 0.3s ease;
        }
        &.active {
            color: var(--clr-dark-blue);
            &::after {
                width: 100%;
            }
        }
    }
}
.title {
    font-size: clamp(1.5rem, calc(1vw + 1.2rem), 2.5rem);
    line-height: 1;
    margin-bottom: 2rem;
}
.description {
    color: var(--clr-gray);
    font-size: 1.25rem;
    max-width: 95%;
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
        left: 0rem;
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
        text-align: center;
        margin-top: 7rem;
    }
    .description {
        text-align: center;
        margin: 0 auto 2rem;
    }
    .cta-container {
        text-align: center;
        justify-content: center;
    }
}
@media (max-width: 767px) {
    .nav {
        .nav-link {
            &.active {
                box-shadow: none;
                &::after {
                    width: 130px;
                }
            }
        }
    }
}
@media (max-width: 575px) {
    .hero-bg {
        width: 85%;
        border-radius: 0 0 8rem 0;
    }
}
</style>
