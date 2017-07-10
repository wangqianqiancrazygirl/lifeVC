<template>
  <footer id="bottombar" class="footer">
    <div>
      <ul id="footermenuNav">
        <li>
          <router-link to="/" class="selected">
            <div class="ico homeico"></div>
            <span class="lispan">首页</span>
          </router-link>
        </li>
        <li>
          <router-link to="/all" class="selected">
            <div class="ico typeico"></div>
            <span>全部产品</span>
          </router-link>
        </li>
        <li>
          <router-link to="/stroll" class="selected">
            <div class="ico strollico"></div>
            <span>闲逛</span>
          </router-link>
        </li>
        <li>
          <router-link to="/cart" class="selected">
            <div class="ico shoppingcartico"></div>
            <span>购物车</span>
          </router-link>
        </li>
        <li>
          <router-link to="/usercenter" class="selected">
            <div class="ico accountcenterico"></div>
            <span>账户中心</span>
          </router-link>
        </li>
      </ul>
    </div>
  </footer>
</template>

<script>
    export default {}
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
