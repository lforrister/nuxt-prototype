<template>
    <div class="eventCardLarge__card">
        <div class="eventCardLarge__header">
            {{ fact[0].fact }}
        </div>
            <!-- {{ $fetchState.pending }} -->
        <LazyImage
            :data="image.message"
            class="eventCardLarge__image"
        />
    </div>
</template>

<script>
import LazyImage from '../LazyImage.vue'

export default {
    components: {
        LazyImage
    },

    data: () => ({
        fact: [],
        image: [],
    }),

    async fetch() {
        this.image = await this.$axios.$get('https://dog.ceo/api/breeds/image/random')
        this.fact = await this.$axios.$get('https://dog-facts-api.herokuapp.com/api/v1/resources/dogs?number=1')
    },

    // fetchOnServer: false,

}
</script>

<style lang="scss">
    .eventCardLarge__card {
        background: white;
    }

    .eventCardLarge__header {
        font-family: Arial;
        padding: 15px 30px;
        font-weight: bold;
        font-size: 30px;
    }


</style>