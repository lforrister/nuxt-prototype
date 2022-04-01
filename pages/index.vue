<template>
  <div class="homePage__container">
    <featured-event
      :facts="facts"
      :image="image.url"
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
    const image  = await $axios.$get('https://random.dog/woof.json')
    return { facts, image }
  }


}
</script>

<style lang="scss">
  .homePage__container {
    @include wrapper;
  }
</style>
