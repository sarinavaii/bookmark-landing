<script setup>
import Button from "@/components/Button.vue";
</script>

<script>
export default {
    data() {
        return {};
    },
};
</script>

<template>
    <section>
        <div class="container-xl">
            <p class="title">35,000+ already joined</p>
            <h2 class="newsletter-title">Stay up-to-date with what we’re doing</h2>
            <form action="">
                <input type="email" placeholder="Enter your email address" />
                <Button type="submit" class="button-red">Contact Us</Button>
            </form>
        </div>
    </section>
</template>

<style lang="scss" scoped>
section {
    background-color: var(--clr-blue);
    padding: 4rem 0;
    color: var(--clr-white);
    text-align: center;
}
.newsletter-title {
    margin: auto;
    max-width: 450px;
    margin-bottom: 2.5rem;
}
.title {
    text-transform: uppercase;
    letter-spacing: 5px;
    font-size: 0.875rem;
    font-weight: 400;
    margin-bottom: 3rem;
}
form {
    justify-content: center;
    display: flex;
    gap: 1rem;
}
input {
    padding: 1rem;
    border: none;
    border-radius: 0.25rem;
    width: min(100%, 300px);
    &::placeholder {
        color: var(--clr-medium-gray);
    }
}
@media (max-width: 575px) {
    form {
        flex-direction: column;
        align-items: center;
    }
}
</style>
