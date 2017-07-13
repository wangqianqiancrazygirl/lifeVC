<template>
  <div>
    <header class="header">
      <div class="header-content">
        <p class="header-title">用户中心</p>
      </div>
      <router-link to="/setting" class="setting">设置</router-link>
    </header>
    <div class="login-or-register">
      <div class="unlisted">
        <p class="state">您还未登录</p>
        <div class="btn-entry">
          <router-link to="/login" class="btn-login">登录</router-link>
          <router-link to="/register">注册</router-link>
        </div>
      </div>
    </div>
    <div class="dashboard-order">
      <ul>
        <li>
          <a href="#">
            <span id="ico1"></span>
            <span class="item-title">待支付</span>
          </a>
        </li>
        <li>
          <a href="#">
            <span id="ico2"></span>
            <span class="item-title">待发货</span>
          </a>
        </li>
        <li class="right">
          <a href="#">
            <span id="ico3"></span>
            <span class="item-title">待收货</span>
          </a>
        </li>
      </ul>
      <ul>
        <li>
          <a href="#">
            <span class="item-ico">
              <span id="ico4"></span>
              <span class="item-title">待评论</span>
            </span>
          </a>
        </li>
        <li>
          <a href="#">
            <span id="ico5"></span>
            <span class="item-title">回复</span>
          </a>
        </li>
        <li class="right">
          <a href="#">
            <span id="ico6"></span>
            <span class="item-title">退换货</span>
          </a>
        </li>
      </ul>
    </div>
    <div class="dashboard">
      <ul style="margin-bottom: 1rem;">
        <li><router-link to="/login"><img src="http://i.lifevccdn.com/upload/centermenuimg/ic_list_cm.png" class="item-i"> <span
          class="item-title">我的订单</span> <span class="arr-r"></span> <!----></router-link></li>
      </ul>
      <ul style="margin-bottom: 1rem;">
        <li><router-link to="/login"><img src="http://i.lifevccdn.com/upload/centermenuimg/ic_coupon_cm.png" class="item-i"> <span
          class="item-title">我的优惠券</span> <span class="arr-r"></span> <!----></router-link></li>
        <li><router-link to="/login"><img src="http://i.lifevccdn.com/upload/centermenuimg/ic_pig_cm.png" class="item-i"> <span
          class="item-title">现金积分</span> <span class="arr-r"></span> <!----></router-link></li>
        <li><router-link to="/login"><img src="http://i.lifevccdn.com/upload/centermenuimg/ic_invoice.png" class="item-i"> <span
          class="item-title">关于发票</span> <span class="arr-r"></span> <!----></router-link></li>
      </ul>
      <ul style="margin-bottom: 1rem;">
        <li><router-link to="/login"><img src="http://i.lifevccdn.com/upload/centermenuimg/i_gear_cm.png" class="item-i"> <span
          class="item-title">密码和登录信息</span> <span class="arr-r"></span> <!----></router-link></li>
        <li><router-link to="/login"><img src="http://i.lifevccdn.com/upload/centermenuimg/i_dialoguebubble3_cm.png" class="item-i"> <span
          class="item-title">老会员建议</span> <span class="arr-r"></span> <!----></router-link></li>
        <li><router-link to="/login"><img src="http://i.lifevccdn.com/upload/centermenuimg/i_customerservice_cm.png" class="item-i"> <span
          class="item-title">客户服务</span> <span class="arr-r"></span> <!----></router-link></li>
        <li><router-link to="/login"><img src="http://i.lifevccdn.com/upload/centermenuimg/ic_currentnode_cm.png" class="item-i"> <span
          class="item-title">地址管理</span> <span class="arr-r"></span> <!----></router-link></li>
        <li><router-link to="/login"><img src="http://i.lifevccdn.com/upload/centermenuimg/sms_cm.png" class="item-i"> <span
          class="item-title">手机验证</span> <span class="arr-r"></span> <!----></router-link></li>
      </ul>
    </div>
  </div>
</template>

<script>
  export default {}
</script>

<style lang="stylus" rel="stylesheet/stylus">
  header
    padding: 0;
    width: 100%;
    height: 50px
    line-height 50px
    text-align center
    font-size 20px
    color white
    background: #89be48;
    position: fixed;
    top: 0;
    z-index: 999;
    .setting
      font-size: 18px;
      color: #fff;
      margin-right: 2%;
      position: absolute;
      right: 2%;
      top: 0;
      z-index: 9;
  .login-or-register
    width 100%
    margin-top 50px
    height: 108px;
    background-image: url(./background.png);
    background-size: 100% 100%;
    .unlisted
      width: 100%;
      overflow: hidden;
      text-align: center;
      margin: 0 auto;
      .state
        text-align: center;
        font-size: 16px;
        line-height: 50px;
        color: #222;
      .btn-entry
        display: inline-block;
        padding: 0 20px;
        height: 36px;
        background: hsla(0, 0%, 100%, .4);
        border: 1px solid #009c42;
        border-radius: 18px;
        margin: 0 auto;
        text-align: center;
        font-size: 16px;
        line-height: 36px;
        .btn-login:after
          content ''
          display inline-block
          width 1px
          height 12px
          margin 0 5px 0 8px
          background-color: #009c42
        a
          color #009c42
  .dashboard-order
    width: 100%;
    overflow: hidden;
    background-color: #fff;
    border-top: 1px solid #eee;
    margin: 0 auto;
    ul
      width: 100%;
      height: 60px;
      overflow: hidden;
      border-bottom: 1px solid #eee;
      margin: 0;
      li
        width: 33%;
        height: 30px;
        float: left;
        border-right: 1px solid #dedede;
        line-height: 24px;
        margin: 16px 0 0;
        padding: 0;
        &.right
          border-right none
        a
          display: block;
          text-align: center;
          color: #585858;
          text-decoration: none;
          padding: 0;
          #ico1, #ico2, #ico3, #ico4, #ico5, #ico6
            display: inline-block;
            height: 36px;
            width: 42px;
            background-repeat: no-repeat;
            background-size: 99% 120%;
            vertical-align middle
          #ico1
            background-position: -5px -7px;
            background-image: url('./notpayment.png')
          #ico2
            background-position: 2px -7px;
            background-image: url('./notdelivery.png')
          #ico3
            background-position: -2px -7px;
            background-image: url('./notreceived.png')
          #ico4
            background-position: -6px -7px;
            background-image: url('./notcomment.png')
          #ico5
            background-position: -6px -4px;
            background-image: url('./response.png')
          #ico6
            background-position: -6px -7px;
            background-image: url('./returns.png')
  .dashboard
    ul
      li
        width: 100%;
        height: 60px;
        overflow: hidden;
        background-color: #fff;
        border-bottom: 1px solid #eee;
        border-top: 1px solid #eee;
        margin: -1px auto 0;
        a
          width: 100%;
          height: 60px;
          display: block;
          .item-i
            width: 2.5rem;
            overflow: hidden;
            display: inline-block;
            float: left;
            margin: 10px 12px 0;
          .item-title
            display: inline-block;
            line-height: 60px;
            text-decoration: none;
            float: left;
            vertical-align: 0;
            font-size: 16px;
            color: #585858;
          .arr-r
            width: 10px;
            height: 10px;
            display: inline-block;
            float: right;
            border-right: 2px solid #bbb;
            border-top: 2px solid #bbb;
            margin: 25px 10px 0 0;
            transform: rotate(45deg);
            -ms-transform: rotate(45deg);
            -moz-transform: rotate(45deg);
            -webkit-transform: rotate(45deg);
</style>
