<template>
  <div>
    <header class="header">
      <div class="header-content">
        <p class="header-title">闲逛</p>
      </div>
    </header>
    <div class="scroll-main">
      <scrollList></scrollList>
      <scrollList></scrollList>
    </div>
  </div>
</template>

<script>
  import scrollList from '../scrollList/scrollList.vue'
  export default {
    components: {
      scrollList
    }
  }
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
  .scroll-main
    margin-top 50px
</style>
