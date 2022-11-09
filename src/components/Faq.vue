<script setup>
import Button from "@/components/Button.vue";
</script>

<script>
export default {
    data() {
        return {
            faqs: [
                {
                    question: "What is Bookmark?",
                    answer: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce tincidunt justo eget ultricies fringilla. Phasellus blandit ipsum quis quam ornare mattis.",
                },
                {
                    question: "How can I request a new browser? ",
                    answer: "Vivamus luctus eros aliquet convallis ultricies. Mauris augue massa, ultricies non ligula. Suspendisse imperdiet. Vivamus luctus eros aliquet convallis ultricies. Mauris augue massa, ultricies non ligula. Suspendisse imperdie tVivamus luctus eros aliquet convallis ultricies. Mauris augue massa, ultricies non ligula. Suspendisse imperdiet.",
                },
                {
                    question: "Is there a mobile app?",
                    answer: "Sed consectetur quam id neque fermentum accumsan. Praesent luctus vestibulum dolor, ut condimentum urna vulputate eget. Cras in ligula quis est pharetra mattis sit amet pharetra purus. Sed sollicitudin ex et ultricies bibendum.",
                },
                {
                    question: "What about other Chromium browsers?",
                    answer: " Integer condimentum ipsum id imperdiet finibus. Vivamus in placerat mi, at euismod dui. Aliquam vitae neque eget nisl gravida pellentesque non ut velit.",
                },
            ],
        };
    },
};
</script>

<template>
    <section>
        <div class="container-xl">
            <h2 class="section-title text-center">Frequently Asked Questions</h2>
            <p class="section-subtitle text-center">
                Here are some of our FAQs. If you have any other questions you’d like answered please feel free to email
                us.
            </p>
            <div class="accordion accordion-flush" id="faq-accordion">
                <div class="accordion-item" v-for="(faq, index) in faqs" :key="index">
                    <h2 class="accordion-header">
                        <button
                            :class="[`accordion-button ${index !== 0 ? 'collapsed' : ''}`]"
                            type="button"
                            data-bs-toggle="collapse"
                            :data-bs-target="[`#q-${index}`]"
                        >
                            {{ faq.question }}
                            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="12">
                                <path fill="none" stroke="#5267DF" stroke-width="3" d="M1 1l8 8 8-8" />
                            </svg>
                        </button>
                    </h2>
                    <div
                        :id="[`q-${index}`]"
                        :class="[`accordion-collapse collapse ${index == 0 ? 'show' : ''}`]"
                        data-bs-parent="#faq-accordion"
                    >
                        <div class="accordion-body">
                            {{ faq.answer }}
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
section {
    margin: 10rem auto;
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
.accordion {
    width: min(100%, 600px);
    margin: auto;
    .accordion-button {
        display: flex;
        justify-content: space-between;
        gap: 1rem;
        font-size: 1.125rem;
        box-shadow: none;
        color: var(--clr-black);
        &::after {
            display: none;
        }
        svg {
            transition: all 0.3s ease;
            flex-shrink: 0;
        }
        &:hover {
            color: var(--clr-red);
        }
        &:not(.collapsed) {
            background-color: var(--clr-white);
            svg {
                transform: rotate(180deg);
                path {
                    stroke: var(--clr-red);
                }
            }
        }
    }
    .accordion-body {
        font-size: 1rem;
        line-height: 2;
        color: var(--clr-dark-blue);
    }
}
</style>
