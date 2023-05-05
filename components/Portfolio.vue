<template>
    <section id="portfolio" class="px py">
        <div class="section-header-top">
            <h2>Featured</h2>
            <div class="header-bar"></div>
        </div>
        <h2 class="text-highlight">Projects</h2>
        <div class="projects-list">
            <ProjectCard v-for="(project, index) of projects" :key="index" :project="project"></ProjectCard>
        </div>
    </section>
</template>

<script lang="ts">
    import { defineComponent } from 'vue';
    import { projectsData } from '@/constants/projects'
    import { Project } from '@/interfaces/Project';

    export default defineComponent({
        name: 'Portfolio',
        data() {
            return {
                projects: projectsData as Project[],
            }
        },
    })
</script>

<style lang="scss">
    @media screen and (min-width: 0px) {
        #portfolio {
            background-color: var(--color-white);
            .projects-list {
                list-style: none;
                padding: 0;
                display: grid;
                grid-template-columns: 1fr;
                gap: 2rem;
                margin-top: 5rem;
            }
            .header-bar {
                width: 20rem;
            }
        }
    }
    @media screen and (min-width: 768px) {
        #portfolio {
            .header-bar {
                width: 47rem;
            }
            .projects-list {
                grid-template-columns: 1fr 1fr;
                gap: 1rem;
            }
        }
    }
    @media screen and (min-width: 1180px) {
        #portfolio {
            .header-bar {
                width: 44rem;
            }
        }
    }
    @media screen and (min-width: 1800px) {
        #portfolio {
            .header-bar {
                width: 54rem;
            }
        }
    }
</style>