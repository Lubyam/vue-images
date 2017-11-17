<template>
  <div class="gallery">

    <div class="wrapper" v-for="(item, index) in images" >
      <img
        v-bind:src="item.imageUrl"
        class="lazyload"
        @click="setActive(index)"
        v-if="showOnlyOne?index == 0: true"
      >
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  export default {
    props: {
      images: Array,
      showOnlyOne: Boolean
    },
    methods: {
      setActive (idx) {
        this.$emit('changeIndex', idx)
      }
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus" scoped>
  .gallery
    display: flex
    flex-wrap: wrap
    .wrapper
      flex: 1
      box-sizing: border-box
      padding: 2px 1px
      img
        display: block
        height: 282px
        width: 301px
        border: 0px
        border-radius: 2px
        cursor: pointer
        overflow: hidden
</style>
