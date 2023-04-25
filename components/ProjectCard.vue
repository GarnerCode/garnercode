<template>
    <div class="project-card" v-if="project">
        <img class="thumbnail" :src="project.imageUrl" :alt="project.title + ' thumbnail'">
        <div class="card-text">
            <div class="title-link-row">
                <h3 class="text-highlight">{{ project.title }}</h3>
                <div class="links-container">
                    <a class="project-link" :href="project.gitUrl" target="_blank">
                                <font-awesome-icon :icon="['fab', 'square-github']" />
                    </a>
                    <a class="project-link" :href="project.liveUrl" target="_blank">
                        <font-awesome-icon :icon="['fas', 'arrow-up-right-from-square']" />
                    </a>
                </div>
            </div>
            <p class="project-description">{{ project.description }}</p>
            <ul class="project-tech-list">
                <li class="project-tech" v-for="(tech, index) of project.tech" :key="index">
                    {{ tech }}
                </li>
            </ul>
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
            display: flex;
            flex-direction: column;
            .thumbnail {
                display: block;
                width: 100%;
                box-shadow: var(--image-box-shadow);
                border-radius: var(--border-radius);
            }
            .card-text {
                background-color: var(--color-black);
                color: var(--color-white);
                border-bottom-left-radius: var(--border-radius);
                border-bottom-right-radius: var(--border-radius);
                position: relative;
                left: 10px;
                padding: 2rem;
            }
            .title-link-row {
                display: flex;
                flex-direction: row;
                justify-content: space-between;
                align-items: center;
            }
            .links-container {
                display: flex;
                flex-direction: row;
                gap: 3rem;
            }
            .project-link {
                color: var(--color-white);
                font-size: 3rem;
                transition: color 0.1s ease;
                &:hover {
                    color: var(--color-primary);
                }
            }
            .project-description {
                height: auto;
            }
            .project-tech-list {
                list-style: none;
                padding: 0;
                display: flex;
                flex-direction: row;
                flex-wrap: wrap;
                gap: 2rem;
            }
            .project-tech {
                font-style: italic;
                font-size: 12px;
            }
        }
    }
    @media screen and (min-width: 768px) {
        .project-card {
            flex-direction: row;
            .thumbnail {
                width: 30rem;
            }
            .card-text {
                border-radius: 0;
                border-top-right-radius: var(--border-radius);
                border-bottom-right-radius: var(--border-radius);
                left: 0;
                top: 10px;
                width: 100%;
            }
            .project-description {
                height: 16rem;
            }
        }
    }
    @media screen and (min-width: 1180px) {
        .project-card {
            .project-description {
                height: 17.7rem;
            }
        }
    }
    @media screen and (min-width: 1800px) {
        .project-card {
            .project-description {
                height: 18.6rem;
            }
        }
    }
</style>