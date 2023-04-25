<template>
    <div id="about-page" class="px py">
        <div class="page-header">
            <div class="header-top">
                <h2>About</h2>
                <div class="header-bar"></div>
            </div>
            <h2 class="text-highlight">Tyler Garner</h2>
        </div>
        <div class="page-content">
            <section>
                <img :src="aboutData.headshotUrl" alt="Headshot image">
                <div class="section-text">
                    <p v-for="(paragraph, index) of aboutData.detailsParagraphs" :key="index">
                        {{ paragraph }}
                    </p>
                </div>
            </section>
            <div class="button-container">
                <nuxt-link class="button" to="/contact">Contact</nuxt-link>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
    import Vue from 'vue'
    import { aboutData } from '@/constants/about';

    export default Vue.extend({
        name: 'AboutPage',
        data() {
            return {
                aboutData,
            }
        }
    })
</script>

<style lang="scss">
    @media screen and (min-width: 0px) {
        #about-page {
            background-color: var(--color-white);
            color: var(--color-black);
            padding-top: 15rem;
            .header-top {
                display: flex;
                flex-direction: row;
                justify-content: space-between;
                align-items: center;
            }
            .header-bar {
                width: 26rem;
            }
            .page-content {
                margin-top: 5rem;
                img {
                    box-shadow: var(--image-box-shadow);
                    width: 100%;
                    border-radius: var(--border-radius);
                    margin-bottom: 5rem;
                }
                p {
                    text-align: justify;
                }
            }
        }
    }
    @media screen and (min-width: 768px) {
        #about-page {
            .header-bar {
                width: 54rem;
            }
            .page-content {
                img {
                    width: 25rem;
                    height: 25rem;
                    display: block;
                    margin-left: auto;
                    margin-right: auto;
                }
                .button-container {
                    display: flex;
                    flex-direction: row;
                    justify-content: flex-end;
                }
            }
        }
    }
    @media screen and (min-width: 1180px) {
        #about-page {
            .header-bar {
                width: 50rem;
            }
        }
    }
    @media screen and (min-width: 1800px) {
        #about-page {
            .header-bar {
                width: 61rem;
            }
        }
    }
</style>