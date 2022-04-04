<template>
    <figure class="lazyImage__image-wrapper" :class="ratio">
        <img 
            class="lazyImage__image lazyload"
            :src="placeholder" 
            :data-src="data" 
            :alt="altText" />
    </figure>
</template>

<script>

export default {

  props: {
      placeholder: {
          type: String,
          default: 'https://via.placeholder.com/850x400.png',
      },
      data: {
          type: String,
          default: 'https://via.placeholder.com/850x400.png'
      },
      altText: {
          type: String,
          default: 'Alt Text'
      },
      ratio: {
          type: String,
          default: 'full',
      },
  }
}
</script>

<style lang="scss">
    .lazyImage__image-wrapper {
       position: relative;
        overflow: hidden;
        margin: 0;

        &.eventCardLarge__image {
            width: 100%;
            height: 0;
            padding-bottom: 50%;
            padding-bottom: 50%;
        }
    }

    .lazyImage__image {
        object-fit: cover;
        object-position: center;
        position: absolute;
        left: 50%;
        transform: translateX(-50%);
        width: 100%;
        height: 100%;
    }
</style>