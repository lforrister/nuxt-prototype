<template>
  <div class="homePage__container">
    <featured-event
      :facts="facts"
      :image="image.message"
    />
  </div>
</template>

<script>
import FeaturedEvent from '../components/HomePage/FeaturedEvents.vue'

export default {
  name: 'IndexPage',

  components: {
    FeaturedEvent,
  },

  async asyncData({$axios}) {
    const facts = await $axios.$get('https://dog-facts-api.herokuapp.com/api/v1/resources/dogs?number=3')
    const image  = await $axios.$get('https://dog.ceo/api/breeds/image/random')
    return { facts, image }
  }


}
</script>

<style lang="scss">
  .homePage__container {
    @include wrapper;
  }
</style>
