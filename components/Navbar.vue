<template>
    <header :class="{'scrolled': scrolled}" id="header">
        <div @click="$router.push('/')" class="logo-container">
            <img src="@/static/assets/images/garnercode-logo-full.svg" alt="Logo">
        </div>
        <div @click="navToggled = !navToggled" :class="{'toggled': navToggled}" class="mobile-nav-button">
            <div class="line1"></div>
            <div class="line2"></div>
            <div class="line3"></div>
        </div>
        <Transition name="slide" mode="out-in">
            <nav class="mobile-nav" v-if="navToggled">
                <ul class="nav-list">
                    <li 
                        :class="{'active': $nuxt.$route.fullPath.includes(nav.label.toLocaleLowerCase()) || (nav.label === 'Home' && $nuxt.$route.fullPath === '/')}"
                        @click="navToggled = false" 
                        class="nav-item" 
                        v-for="(nav, index) of navData" 
                        :key="index"
                    >
                        <nuxt-link v-if="nav.label !== 'Resume'" class="nav-link" :to="nav.route">{{ nav.label }}</nuxt-link>
                        <a v-if="nav.label === 'Resume'" class="nav-link" href="https://drive.google.com/file/d/1qYOm6YzFNQimXF87O818Nmb5PVQXub_m/view" target="_blank">Resume</a>
                    </li>
                </ul>
            </nav>
        </Transition>
        <nav class="desktop-nav">
            <ul class="nav-list">
                <li
                    :class="{'active': $nuxt.$route.fullPath.includes(nav.label.toLocaleLowerCase()) || (nav.label === 'Home' && $nuxt.$route.fullPath === '/')}"
                    class="nav-item"
                    v-for="(nav, index) of navData"
                    :key="index"
                >
                    <nuxt-link v-if="nav.label !== 'Resume'" class="nav-link" :to="nav.route">{{ nav.label }}</nuxt-link>
                    <a v-if="nav.label === 'Resume'" class="nav-link" href="https://drive.google.com/file/d/1qYOm6YzFNQimXF87O818Nmb5PVQXub_m/view" target="_blank">Resume</a>
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
                prevScrollPos: 0,
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
                // let currentScrollPos = window.scrollY;
                // const headerEl = document.getElementById("header")
                // if (headerEl && !this.navToggled) {
                //     if (this.prevScrollPos > currentScrollPos) {
                //         headerEl.style.top = "0"!;
                //     } else {
                //         headerEl.style.top = "-200px"!;
                //     }
                // }
                // this.prevScrollPos = currentScrollPos;
            },
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
            padding: 0 4rem;
            position: fixed;
            top: 0;
            z-index: 100;
            width: calc(100vw - 8rem);
            background-color: var(--color-black);
            transition: all 0.3s ease;
            height: 70px;
            opacity: 0;
            animation: fadeIn 0.3s 0.25s ease forwards;
            &.scrolled {
                box-shadow: 0px 5px 15px -5px rgba(34, 39, 46, 0.5);
            }
            .logo-container {
                font-size: 3rem;
                font-family: var(--font-family-secondary);
                color: var(--color-white);
                display: flex;
                flex-direction: row;
                align-items: flex-start;
                cursor: pointer;
                img {
                    width: 20rem;
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
            .mobile-nav {
                background-color: var(--color-black);
                position: fixed;
                top: 70px;
                left: 0;
                padding: 2rem 4rem;
                padding-top: 0;
                width: calc(100vw - 4rem);
                box-shadow: 0px 5px 15px -5px rgba(34, 39, 46, 0.5);
                .nav-list {
                    padding: 0;
                    list-style: none;
                    display: flex;
                    flex-direction: column;
                    justify-content: space-between;
                    gap: 5rem;
                }
                .nav-item {
                    a {
                        letter-spacing: 2px;
                    }
                    &.active {
                        a {
                            color: var(--color-primary);
                        }
                    }
                }
                .nav-link {
                    text-decoration: none;
                    color:var(--color-white);
                    font-family: var(--font-family-secondary);
                    font-size: 4.5rem;
                }
            }
            .desktop-nav {
                display: none;
            }
        }
        .slide-enter, .slide-leave-to {
            opacity: 0;
            transform: translateY(-2rem);
        }
        .slide-enter-active, .slide-leave-active {
            transition: all 0.3s ease;
        }
    }
    @media screen and (min-width: 768px) {
        header {
            padding: 0 10rem;
            width: calc(100vw - 20rem);
            .mobile-nav {
                padding: 2rem 10rem;
                width: calc(100vw - 20rem);
            }
        }
    }
    @media screen and (min-width: 1180px) {
        header {
            padding: 0 25rem;
            width: calc(100vw - 50rem);
            .logo-container {
                font-size: 2rem;
                img {
                    width: 15rem;
                }
            }
            .mobile-nav-button {
                display: none;
            }
            .desktop-nav {
                display: block;
                .nav-list {
                    list-style: none;
                    padding: 0;
                    display: flex;
                    flex-direction: row;
                    justify-content: space-between;
                    gap: 3rem;
                }
                .nav-item {
                    .nav-link {
                        text-decoration: none;
                        color: var(--color-white);
                        font-size: 1.6rem;
                        font-family: var(--font-family-secondary);
                        transition: all 0.3s ease;
                        letter-spacing: 2px;
                    }
                    &.active {
                        a {
                            color: var(--color-primary);
                        }
                    }
                    &:hover {
                        a {
                            color: var(--color-primary);
                        }
                    }
                }
            }
        }
    }
    @media screen and (min-width: 1400px) {
        header {
            padding: 0 35rem;
            width: calc(100vw - 70rem);
        }
    }
    @media screen and (min-width: 1800px) {
        header {
            padding: 0 40rem;
            width: calc(100vw - 80rem);
        }
    }
</style>