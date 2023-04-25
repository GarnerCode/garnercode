<template>
    <section id="portfolio" class="px py">
        <div class="section-header-top">
            <h2>Past</h2>
            <div class="header-bar"></div>
        </div>
        <h2 class="text-highlight">Projects</h2>
        <ul class="projects-list">
            <li class="project" v-for="(project, index) of projectsData" :key="index">
                <div class="project-image-container">
                    <img class="project-image" :src="project.imageUrl" :alt="project.title + ' thumbnail'">
                </div>
                <div class="project-text">
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
            </li>
        </ul>
    </section>
</template>

<script lang="ts">
    import { defineComponent } from 'vue';
    import { projectsData } from '@/constants/projects'

    export default defineComponent({
        name: 'Portfolio',
        data() {
            return {
                projectsData,
            }
        }
    })
</script>

<style lang="scss">
    @media screen and (min-width: 0px) {
        #portfolio {
            background-color: var(--color-white);
            .projects-list {
                list-style: none;
                padding: 0;
                display: flex;
                flex-direction: column;
                gap: 10rem;
                margin-top: 5rem;
            }
            .project {
                display: flex;
                flex-direction: column;
            }
            .project-image {
                display: block;
                width: 100%;
                box-shadow: var(--image-box-shadow);
                border-radius: var(--border-radius);
            }
            .project-text {
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
            }
            .project-tech-list {
                list-style: none;
                padding: 0;
                display: flex;
                flex-direction: row;
                gap: 2rem;
            }
            .project-tech {
                font-style: italic;
                font-size: 12px;
            }
        }
    }
</style>