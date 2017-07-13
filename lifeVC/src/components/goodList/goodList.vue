<template>
  <ul class="goodsList" v-if="goods">
      <li class="good" v-for="good in goods.goodsList">
        <router-link :to="`/channelsub/${good.id}`">
          <img :src="good.image" alt="">
          <div class="description">{{good.name}}</div>
        </router-link>
      </li>
  </ul>
</template>

<script>
    export default {
      props:['goods'],
      computed: {

      }
    }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  .goodsList
    background: #fff;
    overflow hidden
    .good
      float: left;
      width: 33%;
      height: 150px
      text-align: center;
      border: 1px solid #f1f1f1;
      margin: 0 0 -1px -1px;
      padding-bottom 5px
      img
        width 96%
        margin 0 2%
      .description
        text-align center
        font-size 13px
        padding-bottom 12px
</style>
