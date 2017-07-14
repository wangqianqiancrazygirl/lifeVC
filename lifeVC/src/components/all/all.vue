<template>
  <div>
    <header>
      <div class="header-content">
        <p class="header-title">全部产品</p>
      </div>
      <div class="page-search">
        <mt-search v-model="value" placeholder="搜索商品" :result="filterResult"></mt-search>
      </div>
    </header>
    <div id="content-wrap">
      <div class="life-module">
        <goods :allGoods="goodsList"></goods>
      </div>
    </div>
  </div>
</template>

<script>
  import Vue from 'vue'
  import { Search } from 'mint-ui'
  import goods from '../goods/goods.vue'
  Vue.component('mt-search', Search)
  export default {
    name: 'page-search',
    props:{
      allGoods: Array
    },
    data() {
      return {
        value: '',
        defaultResult: [
          'Apple',
          'Banana',
          'Orange',
          'Durian',
          'Lemon',
          'Peach',
          'Cherry',
          'Berry',
          'Core',
          'Fig',
          'Haw',
          'Melon',
          'Plum',
          'Pear',
          'Peanut',
          'Other'
        ]
      };
    },
    computed: {
      filterResult() {
        return this.defaultResult.filter(value => new RegExp(this.value, 'i').test(value));
      },
      goodsList () {
        this.allGoods.pop()
        return this.allGoods
      }
    },
    components: {
      goods
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
    max-width: 640px
    margin: auto
    .header-content
      width: 100%
      margin: 0 auto
      position: relative
      .header-title
        margin: 0 auto
        line-height: 48px
        font-size: 20px
        text-align: center
        color: #fff
        width: 80%
        white-space: nowrap
        text-overflow: ellipsis
        overflow: hidden
    .page-search
      height: 52px;
      .mint-search
        height: 100%
        input::-webkit-input-placeholder
          text-align center
        input:focus::-webkit-input-placeholder
          text-align left
        .mint-searchbar
          position: relative;
          -webkit-box-align: center;
          -ms-flex-align: center;
          align-items: center;
          background-color: #f2f2f2
          box-sizing: border-box;
          display: -webkit-box;
          display: -ms-flexbox;
          display: flex;
          padding: 8px 10px;
          z-index: 1;
          .mint-searchbar-inner
            -webkit-box-align: center;
            align-items: center;
            background-color: #fff;
            border-radius: 2px;
            display: flex;
            -webkit-box-flex: 1;
            flex: 1;
            height: 28px;
            padding: 4px 6px;
            .mintui-search
              font-size: 20px;
              color: #d9d9d9;
              &:before
                content: "";
                display inline-block
                width:20px;
                height:20px
                background-image: url('./search.png')
                -webkit-background-size: 20px 20px
                background-size: 20px 20px
            .mint-searchbar-core
              -webkit-appearance: none;
              -moz-appearance: none;
              appearance: none;
              border: 0;
              box-sizing: border-box;
              width: 100%;
              height: 100%;
              outline: none
          .mint-searchbar-cancel
            color: #89be48
            margin-left: 10px;
            text-decoration: none;

  .content-wrap
    position: absolute;
    width: 100%;
    top: 96px;
    height: 516px;
    overflow-y: scroll;
</style>
