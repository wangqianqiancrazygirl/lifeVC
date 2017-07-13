<template>
    <footer>
      <ul>
        <li>
          <router-link to="/home">
            <div class="icon homeIcon"></div>
            <span>首页</span>
          </router-link>
        </li>
        <li>
          <router-link to="/all">
            <div class="icon allIcon"></div>
          <span>全部产品</span>
          </router-link>
        </li>
        <li>
          <router-link to="/stroll">
            <div class="icon strollIcon"></div>
            <span>闲逛</span>
          </router-link>
        </li>
        <li>
          <router-link to="/cart">
            <div class="icon cartIcon"></div>
            <span>购物车</span>
          </router-link>
        </li>
        <li>
          <router-link to="/usercenter">
            <div class="icon userIcon"></div>
            <span>账户中心</span>
          </router-link>
        </li>
      </ul>
    </footer>
</template>

<script>
  export default {

  }
</script>

<style lang='stylus' rel='stylesheet/stylus'>
  footer
    position fixed
    height 45px
    bottom 0
    left 0
    right 0
    padding-bottom 1rem
    background #f1f1f1
    ul
      li
        float: left
        width 20%
        a
          display block
          color  #666
          width 100%
          text-align center
          .icon
            height 36px
          .homeIcon
            background url("./home.png") no-repeat center
            background-size 24px
          .allIcon
            background url("./type.png") no-repeat center
            background-size 24px
          .strollIcon
            background url("./scroll.png") no-repeat center
            background-size 24px
          .cartIcon
            background url("./cart.png") no-repeat center
            background-size 24px
          .userIcon
            background url("./account.png") no-repeat center
            background-size 24px
          &.active
            color #009a42
            .homeIcon
              background-image url("./homeactive.png")
            .allIcon
              background-image url("./typeactive.png")
            .strollIcon
              background-image url("./scrollactive.png")
            .cartIcon
              background-image url("./cartactive.png")
            .userIcon
              background-image url("./accountactive.png")
</style>
