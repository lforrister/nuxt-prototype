<template>
    <div class="articleList__container">
        <div v-for="(fact, index) in facts" :key="index">
            <EventCardMed :fact="fact.fact" />
        </div>
    </div>
</template>

<script>
import EventCardMed from '../EventCards/EventCardMed.vue'

export default {
    components: {
        EventCardMed,
    },
    data: () => ({
        facts: [],
    }),

    async fetch() {
        this.facts = await this.$axios.$get('https://dog-facts-api.herokuapp.com/api/v1/resources/dogs?number=8')
    },

    // fetchOnServer: false,

}
</script>

<style lang="scss">
    .articleList__container {
        padding: 30px 0;
    }
</style>