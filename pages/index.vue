<template>
  <div class="homePage__container">
    <FeaturedEvent
      :facts="facts"
      :image="image.message"
    />
    <hr />
    <div class="homePage__main-content">
      <ArticlesList class="homePage__article-list" />
      <div class="homePage__sidebar">
        SIDEBAR 
      </div>
    </div>
    

  </div>
</template>

<script>
import ArticlesList from '../components/HomePage/ArticleList.vue'
import FeaturedEvent from '../components/HomePage/FeaturedEvents.vue'

export default {
  name: 'IndexPage',

  components: {
    ArticlesList,
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

  .homePage__main-content {
    display: flex;
    justify-content: space-between;
  }

  .homePage__article-list {
    @include col-three-quarters;
  }

  .homePage__sidebar {
    @include col-quarter;
  }
</style>
