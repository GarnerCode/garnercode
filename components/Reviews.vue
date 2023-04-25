<template>
    <section id="reviews" class="px py">
        <h2 class="text-highlight">Testimonials</h2>
        <ul class="reviews-list">
            <li class="review" v-for="(review, index) of reviewsData" :key="index">
                <p class="review-quote">"{{ review.quote }}"</p>
                <div class="credit-container">
                    <img class="review-image" :src="review.imageUrl" :alt="review.credit + ' headshot'">
                    <div class="credit-text">
                        <h3>{{ review.credit }}</h3>
                        <div class="credit-position">{{ review.creditPosition }}</div>
                    </div>
                </div>
            </li>
        </ul>
    </section>
</template>

<script lang="ts">
    import { defineComponent } from 'vue';
    import { reviewsData } from '@/constants/reviews';

    export default defineComponent({
        name: 'Reviews',
        data() {
            return {
                reviewsData,
            }
        }
    })
</script>

<style lang="scss">
    @media screen and (min-width: 0px) {
        #reviews {
            background-color: var(--color-black);
            h2 {
                text-align: center;
            }
            .reviews-list {
                list-style: none;
                padding: 0;
            }
            .review {
                color: var(--color-white);
            }
            .review-quote {
                font-style: italic;
                text-align: justify;
                margin-top: 5rem;
            }
            .credit-container {
                display: flex;
                flex-direction: row;
                align-items: center;
                gap: 2rem;
            }
            .review-image {
                border-radius: var(--border-radius);
                width: 10rem;
            }
            .credit-position {
                font-size: 16px;
            }
        }
    }
</style>