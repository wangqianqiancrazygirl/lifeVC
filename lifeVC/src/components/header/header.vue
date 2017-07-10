<template>
  <header class="header">
    <div class="header-content"> </div>
    <div class="wrap-heard">
      <div class="header-icon"></div>
      <router-link to="/all">
        <span class="head-typeimg"></span>
      </router-link>
    </div>
    <div class="menuNav">
      <div class="menuNavNewProductPanel" ref="menuNavNewProductPanel">
        <ul class="menuNavNewProduct" style="width: 800px">
          <li class="font-large" :class="{active: isShow}">
            <router-link to="/home">首页</router-link>
          </li>
          <li class="font-large">
            <router-link to="/new">新品</router-link>
          </li>
          <li class="font-large" v-for="channel in channels">
            <router-link :to='`/channel/${channel.id}`'>{{channel.name}}</router-link>
          </li>
        </ul>
      </div>
    </div>
  </header>
</template>

<script>
   import BScroll from 'better-scroll'
    export default {
      data () {
        return {
          channels: [
            {id: 2860, name: '家务'},
            {id: 2859, name: '下厨'},
            {id: 2865, name: '家居服'},
            {id: 2861, name: '生活'},
            {id: 3260, name: '软装'},
            {id: 2862, name: '床品'},
            {id: 2863, name: '工作和旅游'},
            {id: 2863, name: '了解LifeVC'},
          ],
          isShow: true
        }
      },
      created () {
        this.$nextTick(() => {
          new BScroll(this.$refs.menuNavNewProductPanel, {
            click: true,
            scrollX: true
          })
        })
      }
    }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  header
    padding: 0
    width: 100%
    background: #89be48
    position: fixed
    top: 0
    z-index: 999
    min-width: 320px
    max-width: 768px
    margin: auto
    .wrap-heard
      width: auto
      height: 48px
      background: #89be48
      .header-icon
        display: block
        width: 100%
        height: 48px
        background: url(./logo.png) no-repeat
        background-size: 50%
        background-position: 50%
      .head-typeimg
        width: 44px
        height: 44px
        display: block
        float: right
        position: absolute
        z-index: 1000
        top: 0
        right: 0
        background-size: 45%
        background-image: url(./search.png)
        background-repeat: no-repeat
        background-position: 50%
    .menuNav
      position: relative
      z-index: 1100
      background: #fff
      height: 48px
      .menuNavNewProductPanel
        margin: 0 auto
        position: relative
        width: 100%
        height: 48px
        .menuNavNewProduct
          height: 48px
          float: left
          position: relative
          z-index: 1101
          line-height: 48px
          li
            height: 48px
            float: left
            line-height: 48px
            width: 80px
            text-align: center
            border-bottom: 2px solid #ddd
            &.active
              border-bottom: 2px solid #89be48
              a
                color: #89be48
            a
              height: 48px
              display: block
              padding: 0
              position: relative
              font-size: 14px
</style>
