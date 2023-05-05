<template>
    <div class="project-card" v-if="project">
        <img class="thumbnail" :src="project.imageUrl" :alt="project.title + ' thumbnail'">
        <div class="card-overlay">
            <div class="card-summary">
                <h2 class="text-highlight">{{ project.title }}</h2>
                <p class="card-description">{{ project.description }}</p>
            </div>
            <div class="button-group">
                <div class="card-fine">
                    <p class="fine" v-for="(tech, index) of project.tech" :key="index">{{ tech }}</p>
                </div>
                <a class="button button-primary" target="_blank" :href="project.liveUrl">Visit Site</a>
                <a class="button button-primary" target="_blank" :href="project.gitUrl">View Code</a>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
    import { defineComponent } from 'vue';

    export default defineComponent({
        name: 'ProjectCard',
        props: {
            project: {
                type: Object
            }
        },
    })
</script>

<style lang="scss">
    @media screen and (min-width: 0px) {
        .project-card {
            width: 100%;
            overflow: hidden;
            position: relative;
            border-radius: var(--border-radius);
            box-shadow: var(--image-box-shadow);
            &:hover {
                .thumbnail {
                    transform: scale(1.2);
                }
                .card-overlay {
                    opacity: 1;
                }
            }
            .thumbnail {
                width: 100%;
                transition: 0.3s ease;
            }
            .card-overlay {
                opacity: 0;
                background-color: var(--color-black);
                position: absolute;
                top: 0;
                left: 0;
                width: calc(100% - 4rem);
                height: calc(100% - 4rem);
                padding: 2rem;
                display: flex;
                flex-direction: column;
                justify-content: space-between;
                transition: 0.3s ease;
            }
            .card-description {
                color: var(--color-white);
            }
            .card-fine {
                display: flex;
                flex-direction: row;
                gap: 2rem;
                .fine {
                    color: var(--color-white);
                    font-style: italic;
                    font-size: 12px;
                }
            }
            .button-group {
                display: flex;
                flex-direction: column;
                gap: 1rem;
                .button {
                    width: 100%;
                }
            }
        }
    }
    // @media screen and (min-width: 768px) {
    //     .project-card {
    //         max-width: 37.5rem;
    //         max-height: 37.5rem;
    //     }
    // }
    // @media screen and (min-width: 820px) {
    //     .project-card {
    //         max-width: 38rem;
    //         max-height: 38rem;
    //     }
    // }
</style>