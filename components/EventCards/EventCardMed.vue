<template>
    <div class="eventCardMed__card">
        <div class="eventCardMed__copy">
           <h4 class="eventCardMed__headline">
               {{ fact }}
            </h4>
        </div>
        <LazyImage 
            ratio="quarter"
            class="eventCardMed__image"
            :data="image.message"
        />
    </div>
</template>

<script>
import LazyImage from '../LazyImage.vue'

export default {
    components: {
        LazyImage
    },

    props: {
        fact: {
            type: String,
            default: '',
        }
    },

    data: () => ({
        image: [],
    }),

    async fetch() {
        this.image = await this.$axios.$get('https://dog.ceo/api/breeds/image/random')
    },
}
</script>

<style lang="scss">
    .eventCardMed__card {
        display: flex;
        margin-bottom: 60px;
    }

    .eventCardMed__copy {
        width: 66%;
        padding: 30px;
        background: white;
    }

    .eventCardMed__headline {
        @include h4;
    }

    .eventCardMed__image {
        width: 33%;
    }
</style>