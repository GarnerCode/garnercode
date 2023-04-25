<template>
    <section id="services" class="px py">
        <h2 class="text-highlight">Services</h2>
        <div class="services-container">
            <div class="service">
                <font-awesome-icon :icon="['fas', 'mobile']" />
                <div class="service-label">
                    Mobile-First
                </div>
                <p class="service-description">Develop mobile-first to ensure beautiful layouts across any device.</p>
            </div>
            <div class="service">
                <font-awesome-icon :icon="['fas', 'wifi']" />
                <div class="service-label">
                    Optimization
                </div>
                <p class="service-description">Reduce bounce-rate and retain more visitors to your website with blazing-fast load times.</p>
            </div>
            <div class="service">
                <font-awesome-icon :icon="['fas', 'globe']" />
                <div class="service-label">
                    SEO
                </div>
                <p class="service-description">Boost traffic to your website by implementing the best Search Engine Optimization strategies.</p>
            </div>
        </div>
    </section>
</template>

<script lang="ts">
    import { defineComponent } from 'vue';

    export default defineComponent({
        name: 'Services'
    })
</script>

<style lang="scss">
    #services {
        background-color: var(--color-black);
        h2 {
            text-align: center;
        }
        .services-container {
            display: flex;
            flex-direction: column;
            gap: 3rem;
            margin-top: 5rem;
        }
        .service {
            color: var(--color-white);
            display: flex;
            flex-direction: column;
            justify-content: center;
            text-align: center;
            gap: 1rem;
            svg {
                color: var(--color-primary);
                font-size: 8rem;
            }
            .service-label {
                font-size: 4rem;
                font-family: var(--font-family-secondary);
            }
            .service-description {
                text-align: justify;
            }
        }
    }
</style>