<template>
    <div id="portfolio-page" class="px py">
        <div class="page-header">
            <div class="header-top">
                <h2>All</h2>
                <div class="header-bar"></div>
            </div>
            <h2 class="text-highlight">Projects</h2>
        </div>
        <div class="page-content">
            <ProjectCard 
                v-for="(project, index) of projects" 
                :key="index" 
                :project="project">
            </ProjectCard>
        </div>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { projectsData } from '~/constants/projects';
import { Project } from '@/interfaces/Project';

export default Vue.extend({
    name: 'PortfolioPage',
    data() {
        return {
            projects: projectsData as Project[]
        }
    }
})
</script>

<style lang="scss">
    @media screen and (min-width: 0px) {
        #portfolio-page {
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
                width: 34rem;
            }
            .page-content {
                margin-top: 5rem;
                display: grid;
                grid-template-columns: 1fr;
                gap: 2rem
            }
        }
    }
    @media screen and (min-width: 768px) {
        #portfolio-page {
            .header-bar {
                width: 62rem;
            }
            .page-content {
                grid-template-columns: 1fr 1fr;
                gap: 1rem;
            }
        }
    }
    @media screen and (min-width: 820px) {
        #portfolio-page {
            .header-bar {
                width: 68rem;
            }
        }
    }
    @media screen and (min-width: 1024px) {
        #portfolio-page {
            .header-bar {
                width: 68rem;
            }
        }
    }
    @media screen and (min-width: 1180px) {
        #portfolio-page {
            .header-bar {
                width: 58rem;
            }
        }
    }
</style>