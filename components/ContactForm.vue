<template>
    <form @submit="(e) => handleSubmit(e)" action="https://getform.io/f/607da9e8-ff5a-4f71-9905-0979b0840530" method="POST" class="contact-form">
        <div class="field name-field">
            <input v-model="name" placeholder="Name" class="form-input" type="text" name="name">
        </div>
        <div class="field email-field">
            <input v-model="email" placeholder="Email" class="form-input" type="email" name="email">
        </div>
        <div class="field phone-field">
            <input v-model="phone" placeholder="Phone" class="form-input" type="tel" name="phone">
        </div>
        <div class="field message-field">
            <textarea v-model="message" placeholder="Message" class="form-input" name="message" cols="30" rows="10"></textarea>
        </div>
        <input :class="{'disabled': !isFormComplete()}" class="button" type="submit" value="Submit">
    </form>
</template>

<script lang="ts">
    import { defineComponent } from 'vue';

    export default defineComponent({
        name: 'ContactForm',
        data() {
            return {
                name: '',
                email: '',
                phone: '',
                message: '',
            }
        },
        methods: {
            isFormComplete(): boolean {
                if (
                    this.name === '' ||
                    this.email === '' ||
                    this.message === '' ||
                    this.phone !== ''
                ) {
                    return false;
                }
                return true;
            },
            handleSubmit(e: Event): void {
                if (!this.isFormComplete()) {
                    e.preventDefault();
                }
            },
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
            .phone-field {
                display: none;
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
                border-radius: 0;
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
                cursor: pointer;
                border: 1px solid var(--color-black);
                &.disabled {
                    cursor: not-allowed;
                    background: none;
                    color: var(--color-primary);
                    border: 1px solid var(--color-primary);
                }
            }
        }
    }
    @media screen and (min-width: 768px) {
        .contact-form {
            width: 40rem;
        }
    }
</style>