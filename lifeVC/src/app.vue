<template>
  <div id="top">
    <router-view></router-view>
    <el-footer></el-footer>
    <a class="toTop" target="#top">
    </a>
  </div>
</template>

<script>
  import header from './components/header/header.vue'
  import footer from './components/footer/footer.vue'
  export default {
    components: {
      'el-header': header,
      'el-footer': footer
    },
    created () {

    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  footer
    padding: 0
    height: 55px
    position: fixed
    bottom: 0
    z-index: 900
    width: 100%
    background: #f8f8f8
    border-top: .04rem solid #ddd
    #footermenuNav
      margin: 0
      padding: 0
      background: #f8f8f8
      text-align: center
      li
        width: 20%
        float: left
        margin: 0 auto
        position: relative
  .toTop
    position fixed
    width 30px
    height 30px
    border-radius 50%
    bottom 70px
    overflow hidden
    background rgba(0,0,0,.8)
    border-radius: 50%
    right 2%
    z-index 99
    &::before
      content ''
      display inline-block
      background-color: #fff
</style>
