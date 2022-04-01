<template>
    <div class="eventCardSmall__card">
        <div class="eventCardSmall__header">
           <h3 class="eventCardSmall__number">
               {{ number }} 
           </h3>
           <h4 class="eventCardSmall__headline">
               {{ fact}} 
            </h4>
        </div>
    </div>
</template>

<script>

export default {

  props: {
      fact: {
          type: String,
          default: '',
      },
      number: {
          type: Number,
          default: 1,
      }
  }
}
</script>

<style lang="scss">
    .eventCardSmall__header {
        display: flex;
    }

    .eventCardSmall__number {
        @include h3;
        margin-right: 10px;
    }

    .eventCardSmall__headline {
        @include h4;
    }
</style>