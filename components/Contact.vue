<template>
    <section id="contact" class="px py">
        <h2 class="text-highlight" data-aos="fade-up">Contact</h2>
        <ContactForm data-aos="fade-up"></ContactForm>
    </section>
</template>

<script lang="ts">
    import { defineComponent } from 'vue';

    export default defineComponent({
        name: 'Contact'
    })
</script>

<style lang="scss">
    @media screen and (min-width: 0px) {
        #contact {
            background-color: var(--color-black);
            min-height: 100vh;
            h2 {
                text-align: center;
                margin-bottom: 5rem;
            }
        }
    }
    @media screen and (min-width: 768px) {
        #contact {
            display: flex;
            flex-direction: column;
            align-items: center;
        }
    }
</style>