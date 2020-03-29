<template lang="pug">
  section.global
    div.container-text
      div.container-text__header
        span Label
        ods-switch(
          v-model="value1"
        )
      div.container-text__body
        h1.line-effect Title
        p Lorem Ipsum dolor sit amet, consectetur adipiscing elit.
        ods-button(:round="round") Button
    div.container-img
      div.container-img__clouds
        span 1
      div.container-img__rectangle
        span 2
</template>
<script>
export default {
  name: 'Rakata',
  props: {},

  data () {
    return {
      value1: true,
      round: false
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .global {
    margin: 8rem 3rem;
    display: flex;
    flex-wrap: wrap;
  }
  .container-text {
    flex: 1;
    height: 300px;
    display: flex;
    flex-direction: column;
    &__header {
      display: flex;
      justify-content: space-between;
    }
    &__body {
      h1{
        @extend %tp-r-exa;
        position: relative;
      }
      h1::after {
        width: 120px;
        height: 3px;
        background-color: $--color-primary;
        position: absolute;
      }
      p {
        @extend %tp-r-mega;
      }
    }
  }
  .container-img{
    flex: 1;
    height: 300px;
    &__clouds {
      background-color: red;
    }
    &__rectangle {
      width: 15rem;
      height: 15rem;
      background-color: $--color-secondary;
    }
  }
</style>
