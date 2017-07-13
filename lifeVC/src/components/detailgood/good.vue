<template>
    <div class="wrap-good">
      <div v-if="item" class="good" v-for="good in products">
        <img :src="good.image" alt="">
        <div class="isEmpty" v-show="good.isEmpty">已售空</div>
        <div class="good-info">
          <p class="good-name">
            {{good.name}}
          </p>
          <p>
            <span class="promotion" v-show="good.promotion">限时体验价</span>
            <span class="price">￥ {{good.price}}</span>
            <span class="old-price" v-show="good.oldPrice">￥{{good.oldPrice}}</span>
            <span class="active" v-show="good.active">{{good.active}}</span>
            <span class="comment-count">评论: {{good.commentCount}}</span>
          </p>
        </div>
      </div>
    </div>
</template>

<script>
    export default {
      props: ['item','all'],
      data () {
        return {
        }
      },
      computed: {
        products(){
          console.log(this.item, this.$route.params.id)
          const id = this.$route.params.id
          if(this.item) {
            if(!this.all){
              const good = this.item.goodsList.find(good => {
                return good.id == id
              })
              return good.products
            }else{
              var arr1 = this.item.goodsList[0].products
              // var arr2 = this.item.goodsList[1].products
              /*console.log(arr1, arr2)
               arr1 = [arr1, ...arr2]*/
              // console.log(arr1)
              return arr1
            }
          }
        }
      }
    }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  .wrap-good
    width 100%
    padding-top 24px
    background-color: #f2f2f2
    .good
      position relative
      width: 96%;
      margin 0 auto 24px
      border: 1px solid #ddd;
      img
        display block
        width 100%
      .isEmpty
        width: 84px;
        height: 84px;
        background-color: rgba(0,0,0,.6);
        border-radius: 50%;
        text-align: center;
        vertical-align: middle;
        font-size: 14px;
        color: #fff;
        line-height: 84px;
        font-weight: 700;
        position: absolute;
        left: 50%;
        top: 50%;
        margin-top: -56px;
        margin-left: -42px;
      .good-info
        width 96%
        background: white
        color #333
        padding 2%
        line-height 30px
        .good-name
          font-size 16px
        p
          overflow hidden
          .promotion
            float: left
            display: inline-block;
            background-color: #ff0;
            padding: 1px 3px;
            color #333
            margin-right 8px
          .price
            float left
            margin-right 5px
          .old-price
            text-decoration line-through
            color: #888
          .comment-count
            float: right
          .active
            margin-left 8px
            display: inline-block;
            background-color: #c00;
            padding: 1px 3px;
            color white
</style>
