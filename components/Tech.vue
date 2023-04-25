<template>
    <section id="tech" class="px py">
        <h2 class="text-highlight">Technologies</h2>
        <ul class="tech-list">
            <li class="tech-item" v-for="(tech, index) of aboutData.tech" :key="index">
                <img class="tech-img" :src="tech.imageUrl">
                <div class="tech-label">
                    {{ tech.label }}
                </div>
            </li>
        </ul>
    </section>
</template>

<script lang="ts">
    import { defineComponent } from 'vue';
    import { aboutData } from '@/constants/about';

    export default defineComponent({
        name: 'Tech',
        data() {
            return {
                aboutData,
            }
        }
    })
</script>

<style lang="scss">
    @media screen and (min-width: 0px) {
        #tech {
            background-color: var(--color-black);
            color: var(--color-white);
            h2 {
                text-align: center;
            }
            .tech-list {
                padding: 0;
                list-style: none;
                display: flex;
                flex-direction: row;
                flex-wrap: wrap;
                justify-content: space-evenly;
                gap: 2rem;
                margin-top: 5rem;
            }
            .tech-item {
                font-size: 16px;
                display: flex;
                flex-direction: row;
                align-items: center;
                gap: 1rem;
            }
            .tech-img {
                width: 5rem;
                height: 5rem;
            }
        }
    }
</style>