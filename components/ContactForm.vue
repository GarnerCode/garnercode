<template>
    <form class="contact-form">
        <div class="field">
            <input placeholder="Name" class="form-input" type="text" name="name">
        </div>
        <div class="field">
            <input placeholder="Email" class="form-input" type="email" name="email">
        </div>
        <div class="field">
            <textarea placeholder="Message" class="form-input" name="message" cols="30" rows="10"></textarea>
        </div>
        <input class="button" type="submit" value="Submit">
    </form>
</template>

<script lang="ts">
    import { defineComponent } from 'vue';

    export default defineComponent({
        name: 'ContactForm',
        data() {
            return {

            }
        }
    })
</script>

<style lang="scss">
    @media screen and (min-width: 0px) {
        .contact-form {
            display: flex;
            flex-direction: column;
            gap: 2rem;
            label {
                display: block;

            }
            .form-input {
                display: block;
                font-size: 16px;
                padding: 1.6rem 1rem;
                width: calc(100% - 2rem);
                resize: none;
                background: none;
                color: var(--color-white);
                border: none;
                border-bottom: 1px solid var(--color-white);
                &:focus {
                    outline: none;
                    border-bottom: 1px solid var(--color-primary);
                }
            }
            textarea {
                border: 1px solid var(--color-white) !important;
                border-radius: var(--border-radius);
                &:focus {
                    border: 1px solid var(--color-primary) !important;
                }
            }
            .button {
                margin: 0 auto;
            }
        }
    }
    @media screen and (min-width: 768px) {
        .contact-form {
            width: 40rem;
        }
    }
</style>