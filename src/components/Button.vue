<template>
    <component :is="type" :href="href" class="button">
        <slot />
    </component>
</template>
<script>
export default {
    props: {
        href: {
            type: String,
        },
        text: {
            type: String,
        },
    },
    computed: {
        type() {
            if (this.href) {
                return "a";
            } else {
                return "button";
            }
        },
    },
};
</script>
<style lang="scss">
.button {
    display: inline-block;
    padding: 0.75rem 1.5rem;
    border-radius: 5px;
    font-weight: 500;
    font-size: 0.875rem;
    text-decoration: none;
    background-color: var(--clr-white);
    color: var(--clr-black);
    border: none;
    box-shadow: 0px 5px 15px -10px var(--clr-gray);
    transition: all 0.2s ease;
    &.pure {
        background-color: transparent;
        padding: 0;
        border: none;
        outline: none;
        box-shadow: none;
    }
    &-red {
        border: 2px solid var(--clr-red);
        background-color: var(--clr-red);
        color: var(--clr-white);
        &:hover {
            background-color: var(--clr-white);
            color: var(--clr-red);
        }
    }
    &-blue {
        border: 2px solid var(--clr-blue);
        background-color: var(--clr-blue);
        color: var(--clr-white);
        &:hover {
            background-color: var(--clr-white);
            color: var(--clr-blue);
        }
    }
    &-gray {
        border: 2px solid var(--clr-light-gray);
        background-color: var(--clr-light-gray);
        color: var(--clr-dark-blue);
        &:hover {
            background-color: var(--clr-white);
            color: var(--clr-gray);
            border-color: var(--clr-gray);
        }
    }
}
</style>
