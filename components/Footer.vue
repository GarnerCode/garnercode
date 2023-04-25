<template>
    <footer class="px">
        Footer
    </footer>
</template>

<script lang="ts">
    import { defineComponent } from 'vue';

    export default defineComponent({
        name: 'Footer',
    })
</script>

<style lang="scss">
    @media screen and (min-width: 0px) {
        footer {
            box-shadow: 0px -5px 15px -5px rgba(34, 39, 46, 0.5);
            color: var(--color-white);
            padding-top: 3rem;
            padding-bottom: 3rem;
        }
    }
</style>