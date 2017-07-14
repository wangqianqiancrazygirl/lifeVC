<template>
  <div class="allGoods" v-if="allGoods">
    <div class="goods" v-for="goods in allGoods">
      <div class="goodsTitle">{{goods.type}}</div>
        <goodList :goods="goods"></goodList>
    </div>
  </div>
</template>

<script>
  import goodList from '../goodList/goodList.vue'
  import axios from 'axios'

  export default {
    props:['allGoods'],
    components: {
      goodList
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  .allGoods
    margin-top 100px
    padding-bottom 65px
    .goods
      .goodsTitle
        padding 25px 0 10px 0
        background-color: #f2f2f2
        width: 100%;
        text-align: center;
        font-size 20px
</style>
