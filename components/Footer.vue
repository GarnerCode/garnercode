<template>
    <footer class="px">
        <div class="logo-container">
            <img src="@/static/assets/images/garnercode-logo-full.svg" alt="Logo">
        </div>
        <ul class="links-list">
            <li>
                <a href="https://github.com/GarnerCode" target="_blank">
                    <font-awesome-icon :icon="['fab', 'square-github']" />
                </a>
            </li>
            <li>
                <a href="https://www.linkedin.com/in/tgarner98/" target="_blank">
                    <font-awesome-icon :icon="['fab', 'linkedin']" />
                </a>
            </li>
        </ul>
        <div class="fine">
            Copyright © {{ currentYear }} | Tyler Garner
        </div>
    </footer>
</template>

<script lang="ts">
    import { defineComponent } from 'vue';

    export default defineComponent({
        name: 'Footer',
        data() {
            return {
                currentYear: new Date().getFullYear(),
            }
        }
    })
</script>

<style lang="scss">
    @media screen and (min-width: 0px) {
        footer {
            box-shadow: 0px -5px 15px -5px rgba(34, 39, 46, 0.5);
            color: var(--color-white);
            padding-top: 3rem;
            padding-bottom: 3rem;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 2rem;
            .logo-container {
                font-size: 2rem;
                font-family: var(--font-family-secondary);
                color: var(--color-white);
                display: flex;
                flex-direction: row;
                align-items: flex-start;
                cursor: pointer;
                img {
                    width: 10rem;
                }
                span {
                    font-family: var(--font-family-secondary);
                }
            }
            .links-list {
                list-style: none;
                padding: 0;
                display: flex;
                flex-direction: row;
                gap: 2rem;
                a {
                    color: var(--color-white);
                    font-size: 3rem;
                    transition: color 0.1s ease;
                    &:hover {
                        color: var(--color-primary);
                    }
                }
            }
            .fine {
                font-size: 12px;
                font-style: italic;
            }
        }
    }
</style>