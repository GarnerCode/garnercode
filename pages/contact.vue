<template>
    <div id="contact-page" class="px py">
        <div class="page-header">
            <div class="header-top">
                <h2>Let's</h2>
                <div class="header-bar"></div>
            </div>
            <h2 class="text-highlight">Build Something</h2>
        </div>
        <div class="page-content">
            <div class="form-container">
                <ContactForm></ContactForm>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
    name: 'ContactPage'
})
</script>

<style lang="scss">
    @media screen and (min-width: 0px) {
        #contact-page {
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
                width: 29rem;
            }
            .page-content {
                display: flex;
                flex-direction: column;
                gap: 5rem;
                margin-top: 5rem;
                p {
                    margin: 0;
                }
            }
            .form-container {
                background-color: var(--color-black);
                border-radius: var(--border-radius);
                padding: 2rem;
                box-shadow: var(--image-box-shadow);
                width: calc(100% - 8rem);
                margin: 0 auto;
            }
        }
    }
    @media screen and (min-width: 768px) {
        #contact-page {
            .header-bar {
                width: 57rem;
            }
            .form-container {
                width: fit-content;
            }
        }
    }
    @media screen and (min-width: 1024px) {
        #contact-page {
            .header-bar {
                width: 63rem;
            }
        }
    }
</style>