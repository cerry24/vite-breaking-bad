<script>
import { store } from '../store.js';

export default {
    name: 'ElementCard',

    props: {
        card: {
            type: Object,
            required: true
        }
    },

    data() {
        return {
            store
        }
    },
}
</script>

<template>
    <article class="card" :data-custom-id="card.id">
        <div class="image">
            <img :src="card.card_images[0].image_url" :alt="card.name">
        </div>

        <div class="info">
            <h3>{{ card.name }}</h3>
            <p>{{ card.archetype }}</p>
        </div>
    </article>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;

.card {
    width: calc(100% / 5 - 20px);
    background-color: $main-color;
    margin: 0 20px 20px 0;

    .info {
        text-align: center;
        padding: 15px;

        h3 {
            text-transform: uppercase;
            color: $secondary-color;
            margin-bottom: 10px;
        }
    }
}

img {
    width: 100%;
    object-fit: contain;
}
</style>