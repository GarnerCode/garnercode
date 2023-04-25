<template>
    <section id="about" class="px py">
        <div class="column">
            <img class="headshot" :src="aboutData.headshotUrl" alt="Headshot image">
        </div>
        <div class="column about-text">
            <div class="section-header-top">
                <h2>About</h2>
                <div class="header-bar"></div>
            </div>
            <h2 class="text-highlight">Tyler Garner</h2>
            <p v-for="(paragraph, index) of aboutData.summaryParagraphs" :key="index">{{ paragraph }}</p>
        </div>
    </section>
</template>

<script lang="ts">
    import { defineComponent } from 'vue';
    import { aboutData } from '@/constants/about';

    export default defineComponent({
        name: 'About',
        data() {
            return {
                aboutData,
            }
        }
    })
</script>

<style lang="scss">
    @media screen and (min-width: 0px) {
        #about {
            background-color: var(--color-white);
            display: flex;
            flex-direction: column;
            gap: 5rem;
            .headshot {
                display: block;
                width: 100%;
                box-shadow: var(--image-box-shadow);
                border-radius: var(--border-radius);
            }
            h2 {
                color: var(--color-black);
            }
            p {
                text-align: justify;
                color: var(--color-black);
            }
        }
    }
    @media screen and (min-width: 768px) {
        #about {
            flex-direction: row;
            gap: 7rem;
            .headshot {
                width: 25rem;
            }
            .header-bar {
                width: 23rem;
            }
        }
    }
    @media screen and (min-width: 1180px) {
        #about {
            .header-bar {
                width: 20rem;
            }
        }
    }
    @media screen and (min-width: 1800px) {
        #about {
            .header-bar {
                width: 30rem;
            }
        }
    }
</style>