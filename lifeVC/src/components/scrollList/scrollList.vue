<template>
  <div class="stroll-all-item">
    <div class="stroll-item" v-for="item in scrollList">
      <div class="stroll-type-item">
        <div class="stroll-item-layer">
          <img class="stroll-item-img" :src="item.image">
          <span class="tag-new" v-show="item.isNew">New</span>
        </div>
        <h3 class="stroll-item-title">
          <a href="javascript:void(0);">{{item.title}}</a>
        </h3>
        <div class="stroll-price-bar">
          <span class="price">￥<em>{{item.price}}</em></span>
          <span class="comment">月销 {{item.count}}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        scrollList: [
          {
            "image": "http://i.lifevccdn.com/upload/stroll/e726ff1fb1d44685a91cf76ff56d5018.jpg",
            "title": "分类整理收纳箱",
            "price": 49,
            "oldPrice": "",
            "isNew": true,
            "count": 4082
          },
          {
            "image": "http://i.lifevccdn.com/upload/stroll/06cde94e3e4f4c2093b33fdcb1cb4726.jpg",
            "title": "可挂式防潮除湿剂(8袋装)",
            "price": 30,
            "oldPrice": "",
            "isNew": false,
            "count": 5279
          },
          {
            "image": "http://i.lifevccdn.com/upload/stroll/5b388119f79444ba889c4f6b9a118bad.jpg",
            "title": "加拿大原生木浆抽纸（12包）",
            "price": 29,
            "oldPrice": "",
            "isNew": false,
            "count": 8141
          },
          {
            "image": "http://i.lifevccdn.com/upload/stroll/66986bc8c2d04e61ae6ba5c204872d71.jpg",
            "title": "大容量防潮除湿桶(可重复使用)",
            "price": 19,
            "oldPrice": "",
            "isNew": false,
            "count": 11067
          },
          {
            "image": "http://i.lifevccdn.com/upload/stroll/38226fd7a3c64442bc97b11f5a28dacf.jpg",
            "title": "精梳棉护肤毛巾(莎曼系列)",
            "price": 69,
            "oldPrice": "",
            "isNew": false,
            "count": 4794
          }
        ]
      }
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  .stroll-all-item
    width: 50%;
    float: left;
    padding-bottom 60px
    .stroll-item
      margin: 3%;
      width: 94%;
      clear: both;
      .stroll-type-item
        margin: 0 1%;
        .stroll-item-layer
          position: relative;
          border-radius: 8px;
          .stroll-item-img
            width 100%
          .tag-new
            background-color: #79da87;
            max-width: 94%;
            overflow: hidden;
            display: inline-block;
            text-align: left;
            font-size: 12px;
            color: #fff;
            line-height: 24px;
            text-transform: uppercase;
            padding: 1px;
            position: absolute;
            left: 0;
            top: 8px;
            z-index: 6;
            white-space: nowrap;
            word-break: keep-all;
            text-overflow: ellipsis;
            -o-text-overflow: ellipsis;
      .stroll-item-title
        font-size: .95rem;
        padding: 4px 0 2px;
        overflow: hidden;
        white-space: nowrap;
        word-break: keep-all;
        text-overflow: ellipsis;
        a
          color: #333;
          text-decoration: none;
          font-size: 14px;

      .stroll-price-bar
        text-align: left;
        width: 100%;
        font-size: 20px;
        height: 25px;
        overflow: hidden;
        .price
          font-size: 16px;
          line-height: 30px;
          display: inline-block;
          color: #ff475d;
          font-weight: 400;
          overflow: hidden;
          text-align: left;
          padding: 0 3px
        .comment
          font-size: 14px;
          line-height: 30px;
          width: auto;
          max-width: none;
          overflow: hidden;
          float: right;
          display: inline-block;
          text-align: right;
          color: #999;
          white-space: nowrap;
          word-break: keep-all;
          text-overflow: ellipsis;
          -o-text-overflow: ellipsis;

</style>
