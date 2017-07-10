<template>
  <div>
    <router-view></router-view>
    <el-footer></el-footer>
  </div>
</template>

<script>
  import header from './components/header/header.vue'
  import footer from './components/footer/footer.vue'
  export default {
    components: {
      'el-header': header,
      'el-footer': footer
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
        /*.ico
          width: 100%
          height: 40px
          background-position: 50%
          background-repeat: no-repeat
          background-size: 28%
          margin-bottom: 15px*/

</style>
