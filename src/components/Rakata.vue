<template lang="pug">
  section.global(:class="{ swapContainer: switchChange }")
    div.container-text(:class="{ separation: switchChange }")
      div.container-text__header
        span Label
        ods-switch(
          v-model="switchChange"
        )
      div.container-text__body
        h1.title Title
        p Lorem Ipsum dolor sit amet, consectetur adipiscing elit.
        ods-button Button
    div.container-img
      div.container-img__clouds
        img(src="@/assets/images/virus.jpg" width="100%" height="100%")
      div.container-img__rectangle
</template>
<script>
export default {
  name: 'Rakata',
  props: {},

  data () {
    return {
      switchChange: false
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
    justify-content: space-between;
  }
  .swapContainer {
    flex-direction: row-reverse;
  }
  .separation {
    margin-left: 1rem;
  }
  .container-text {
    width: 48%;
    height: 23rem;
    display: flex;
    flex-direction: column;
    &__header {
      display: flex;
      justify-content: space-between;
      span {
        @extend %tp-r-deca;
      }
    }
    &__body {
      .title{
        @extend %tp-r-exa;
        border-bottom: 3px solid $--color-primary;
        width: 20%;
      }
      p {
        @extend %tp-r-mega;
        padding-bottom: 3rem;
      }
      .ods-button.is-round {
        border-radius: 0px;
      }
    }
  }
  .container-img{
    width: 48%;
    height: 23rem;
    position: relative;
    &__clouds {
      background-color: blue;
      width: 90%;
      height: 90%;
      float: right;
    }
    &__rectangle {
      width: 10rem;
      height: 10rem;
      background-color: $--color-danger;
      z-index: -1;
      position: absolute;
      bottom: 0;
    }
  }
  @media screen and (max-width: 1023px) {
    body {
      font-size: 18px;
    }
    .swapContainer {
      flex-direction: column-reverse;
    }
    .container-text, .container-img{
      width: 100%;
    }
    br {
      display: none;
    }
  }
  @media screen and (max-width: 767px) {
    body {
      font-size: 18px;
    }
    .swapContainer {
      flex-direction: column-reverse;
    }
    .container-text, .container-img{
      width: 100%;
      &__body{
        .ods-button {
          width: 100%;
        }
      }
    }
  }
</style>
