<template>
    <section class="featuredEvents__section">
        <div class="featuredEvents__left">
            <EventCardLarge />
        </div>
        <div class="featuredEvents__right">
            <h3 class="featuredEvents__trending">
                Top & Trending Stories
            </h3>
            <div v-for="(fact, index) in facts" :key="index">
                <EventCardSmall
                    :fact="fact.fact" 
                    :number="index + 1"
                />
            </div>
        </div>
    </section>
</template>

<script>
import EventCardLarge from '../EventCards/EventCardLarge.vue'
import EventCardSmall from '../EventCards/EventCardSmall'

export default {
  components: {
    EventCardLarge,
    EventCardSmall
  },

  props: {
      facts: {
          type: Array,
          default() {
              return []
          },
      },
      image: {
          type: String,
          default: '',
      }

  }
}
</script>

<style lang="scss">
    .featuredEvents__section {
        display: flex;
        justify-content: space-between;
        padding: 30px 0;
    }

    .featuredEvents__left {
        @include col-two-thirds;
    }

    .featuredEvents__right {
        @include col-third;
    }

    .featuredEvents__trending {
        @include h3;
    }

</style>