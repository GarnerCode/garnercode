<template>
    <header :class="{'scrolled': scrolled}">
        <div class="logo-container">
            <img src="@/static/assets/icons/logo.svg">
            arner<span class="text-highlight">Code.io</span>
        </div>
        <div @click="navToggled = !navToggled" :class="{'toggled': navToggled}" class="mobile-nav-button">
            <div class="line1"></div>
            <div class="line2"></div>
            <div class="line3"></div>
        </div>
        <nav v-if="navToggled">
            <ul class="nav-list">
                <li @click="navToggled = false" class="nav-item" v-for="(nav, index) of navData" :key="index">
                    <a class="nav-link" :href="nav.route">{{ nav.label }}</a>
                </li>
            </ul>
        </nav>
    </header>
</template>

<script lang="ts">
    import { defineComponent } from 'vue';
    import { navData } from '@/constants/nav';

    export default defineComponent({
        name: 'Navbar',
        data() {
            return {
                navData,
                navToggled: false,
                scrolled: false,
            }
        },
        mounted() {
            window.addEventListener('scroll', this.handleScroll);
        },
        methods: {
            handleScroll(): void {
                if (window.scrollY) {
                    this.scrolled = true;
                } else {
                    this.scrolled = false;
                }
            }
        },
    })
</script>

<style lang="scss">
    @media screen and (min-width: 0px) {
        header {
            display: flex;
            flex-direction: row;
            justify-content: space-between;
            align-items: center;
            padding: 2rem 4rem;
            position: fixed;
            top: 0;
            width: calc(100vw - 8rem);
            background-color: var(--color-black);
            transition: box-shadow 0.3s ease;
            height: 6rem;
            &.scrolled {
                box-shadow: 0px 5px 15px rgba(34, 39, 46, 0.5);
            }
            .logo-container {
                font-size: 4.5rem;
                font-family: var(--font-family-secondary);
                color: var(--color-white);
                display: flex;
                flex-direction: row;
                align-items: flex-start;
                cursor: pointer;
                img {
                    width: 4rem;
                }
                span {
                    font-family: var(--font-family-secondary);
                }
            }
            .mobile-nav-button {
                cursor: pointer;
                div {
                    width: 25px;
                    height: 3px;
                    background-color: var(--color-white);
                    margin: 5px;
                    transition: all 0.3s ease;
                }
                &.toggled {
                    div {
                        background-color: var(--color-primary);
                    }
                    .line1 {
                        transform: rotate(-45deg) translate(-5px, 6px);
                    }
                    .line2 {
                        opacity: 0;
                    }
                    .line3 {
                        transform: rotate(45deg) translate(-5px, -6px);
                    }
                }
            }
            nav {
                background-color: var(--color-black);
                position: fixed;
                top: 8rem;
                left: 0;
                padding: 2rem 4rem;
                width: calc(100vw - 4rem);
                box-shadow: 0px 5px 15px rgba(34, 39, 46, 0.5);
                .nav-list {
                    padding: 0;
                    list-style: none;
                    display: flex;
                    flex-direction: column;
                    justify-content: space-between;
                    gap: 5rem;
                }
                .nav-link {
                    text-decoration: none;
                    color:var(--color-white);
                    font-family: var(--font-family-secondary);
                    font-size: 4.5rem;
                }
            }
        }
    }
</style>