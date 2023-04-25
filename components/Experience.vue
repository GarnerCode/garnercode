<template>
    <section id="experience" class="px py">
        <div class="section-header-top">
            <h2>Work</h2>
            <div class="header-bar"></div>
        </div>
        <h2 class="text-highlight">Experience</h2>
        <ul class="experience-list">
            <li class="experience-item" v-for="(job, index) of experienceData" :key="index">
                <h3>{{ job.company }}</h3>
                <h3>{{ job.position }}</h3>
                <div class="fine">{{ job.dates }}</div>
            </li>
        </ul>
    </section>
</template>

<script lang="ts">
    import { defineComponent } from 'vue';
    import { experienceData } from '@/constants/experience';

    export default defineComponent({
        name: 'Experience',
        data() {
            return {
                experienceData,
            }
        }
    })
</script>

<style lang="scss">
    @media screen and (min-width: 0px) {
        #experience {
            background-color: var(--color-white);
            .header-bar {
                width: 28rem;
            }
            .experience-list {
                list-style-type: square;
                margin-top: 5rem;
                padding-left: 2.5rem;
            }
            .experience-item {
                padding-left: 2rem;
                h3 {
                    font-size: 3rem;
                    color: var(--color-black);
                }
                &::marker {
                    color: var(--color-primary);
                    font-size: 3rem;
                    content: "▶";
                }
                .fine {
                    font-size: 12px;
                    font-style: italic;
                }
            }
        }
    }
    @media screen and (min-width: 768px) {
        #experience {
            .header-bar {
                width: 56rem;
            }
        }
    }
    @media screen and (min-width: 1180px) {
        #experience {
            .header-bar {
                width: 52rem;
            }
        }
    }
    @media screen and (min-width: 1800px) {
        #experience {
            .header-bar {
                width: 63rem;
            }
        }
    }
</style>