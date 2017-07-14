<template>
  <div id="top">
    <router-view :allGoods="allGoods"></router-view>
    <el-footer></el-footer>
    <!--<a class="toTop" target="#top">
    </a>-->
    <back-top v-show="topValue">
      <i class="icon-top"></i>
    </back-top>
  </div>
</template>

<script>
  import header from './components/header/header.vue'
  import footer from './components/footer/footer.vue'
  import BackTop from './components/backtop/BackTop.vue'
  import axios from 'axios'
  export default {
    data () {
      return {
        topValue: false,
        allGoods: []
      }
    },
    created () {
      window.addEventListener('scroll',function(){
        var scrollTop = document.documentElement.scrollTop || document.body.scrollTop;
        if(scrollTop > 700){
          this.topValue = true
        }else {
          this.topValue = false
        }
      }.bind(this),false)
      axios.get('/goods')
        .then(response => {
          var result = response.data
          if(result.code === 0){
            this.allGoods = result.data
          }
        })
    },
    components: {
      'el-header': header,
      'el-footer': footer,
      BackTop
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
  .icon-top
    position fixed
    width 36px
    height 36px
    border-radius 50%
    bottom 70px
    overflow hidden
    background rgba(0,0,0,.8)
    right 2%
    z-index 99
    &::before
      content ''
      display inline-block
      width 22px
      height 12px
      background: url('../static/img/backtop.png') no-repeat
      -webkit-background-size 22px 12px
      background-size 22px 12px
      margin-top 10px
      margin-left 7px

</style>
