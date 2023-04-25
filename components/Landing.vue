<template>
    <section id="landing" class="px">
        <div class="landing-content">
            <h1>Tyler Garner</h1>
            <h2 class="text-highlight">Web Developer</h2>
            <p>I work with Vue.js to develop complex user interfaces and web applications.</p>
            <NuxtLink class="button" to="/contact">Contact</NuxtLink>
        </div>
    </section>
</template>

<script lang="ts">
    import { defineComponent } from 'vue';

    export default defineComponent({
        name: 'Landing',
    })
</script>

<style lang="scss">
    @media screen and (min-width: 0px) {
        #landing {
            height: 100vh;
            background-color: var(--color-black);
            color: var(--color-white);
            display: flex;
            flex-direction: column;
            justify-content: center;
        }
    }
    @media screen and (min-width: 768px) {
        #landing {
            p {
                width: 35rem;
            }
        }
    }
</style>