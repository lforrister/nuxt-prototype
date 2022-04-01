<template>
    <div class="eventCardLarge__card">
        <div class="eventCardLarge__header">
            {{ fact }}
        </div>

        <div class="eventCardLarge__image-wrapper">
            <img class="eventCardLarge__image" :src="image" />
            <!-- TODO: Do we want to lazy load? skeleton load? etc -->
        </div>

    </div>
</template>

<script>

export default {
    props: {
        image: {
            type: String,
            default: '',
        },
        fact: {
            type: String,
            default: '',
        }

  },
    data: () => ({
        // fact: [],
        // image: [],
    }),

  async fetch() {
    // this.image = await this.$axios.$get('https://random.dog/woof.json')
    // this.fact = await this.$axios.$get('https://catfact.ninja/fact')
  },


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

    .eventCardLarge__image-wrapper {
        width: 100%;
        height: 0;
        padding-bottom: 50%;
        position: relative;
        overflow: hidden;
    }

    .eventCardLarge__image {
        width: 100%;
        position: absolute;
        left: 50%;
        transform: translateX(-50%);
    }

</style>