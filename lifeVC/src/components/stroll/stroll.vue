<template>
  <div>
    <header class="header">
      <div class="header-content">
        <p class="header-title">闲逛</p>
      </div>
    </header>
    <div class="scroll-main">
      <hawk></hawk>
      <template v-if="scrollList">
        <scrollList :filterodd="filterodd"></scrollList>
        <scrollList :filtereven="filtereven"></scrollList>
      </template>
    </div>
  </div>
</template>

<script>
  import scrollList from '../scrollList/scrollList.vue'
  import hawk from '../hawk/hawk.vue'
  import axios from 'axios'

  const OK = 0
  export default {
    data () {
      return {
        scrollList: []
      }
    },
    created () {
      axios.get('/scroll')
        .then(response => {
          console.log(response.data)
          const result = response.data
          if(result.code === OK) {
            this.scrollList = result.data
          }
        })
    },
    computed: {
      filterodd () {
        return this.scrollList.filter((item, index) => {
          return index % 2 === 1
        })
      },
      filtereven () {
        return this.scrollList.filter((item, index) => {
          return index % 2 === 0
        })
      }
    },
    components: {
      scrollList,
      hawk
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
