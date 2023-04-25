<template>
    <section id="contact" class="px py">
        <h2 class="text-highlight">Contact</h2>
        <ContactForm></ContactForm>
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
            h2 {
                text-align: center;
                margin-bottom: 5rem;
            }
        }
    }
</style>