<template>
  <div class="stroll-all-item">
    <div class="stroll-item" v-for="item in filterScroll">
      <div class="stroll-type-item">
        <div class="stroll-item-layer">
          <img class="stroll-item-img" :src="item.image">
          <span class="tag-new" v-show="item.isNew">New</span>
        </div>
        <h3 class="stroll-item-title">
          <a href="javascript:void(0);">{{item.title}}</a>
        </h3>
        <div class="stroll-price-bar">
          <span class="price">
            ￥<em>{{item.price}}</em>
            <span class="original" v-show="item.oldPrice">￥{{item.oldPrice}}</span>
          </span>
          <span class="comment">月销 {{item.count}}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    props:['filterodd', 'filtereven'],
    computed: {
      filterScroll () {
        const {filterodd, filtereven} = this
        return filterodd ? filterodd : filtereven
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
          .original
            font-size: 10px;
            display: inline-block;
            color: #888;
            text-decoration: line-through;
            margin-left: 5px;
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
