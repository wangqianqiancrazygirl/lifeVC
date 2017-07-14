<template>
  <div>
    <el-header></el-header>
    <article class="home-body">
      <div class="page-loadmore-wrapper">
        <div class="mint-loadmore">
          <div class="mint-loadmore-content">
            <div class="mint-loadmore-top">
              <span class="mint-loadmore-text">下拉刷新</span>
            </div>
            <div class="autoPlay">
              <swiper :options="swiperOption" ref="mySwiper">
                <!-- slides -->
                <swiper-slide>
                  <img src="./image01.jpg" alt="">
                </swiper-slide>
                <swiper-slide>
                  <img src="./image02.jpg" alt="">
                </swiper-slide>
                <swiper-slide>
                  <img src="./image03.jpg" alt="">
                </swiper-slide>
                <swiper-slide>
                  <img src="./image04.jpg" alt="">
                </swiper-slide>
                <swiper-slide>
                  <img src="./image05.jpg" alt="">
                </swiper-slide>
                <!-- Optional controls -->
                <div class="swiper-pagination"  slot="pagination"></div>
              </swiper>
            </div>
            <div class="item-combo" v-for="item in items">
              <div class="img-wrap" :style="`{height: ${item.height}}`">
                <img :usemap="`#${item.id}`"
                     :src="item.image"
                     style="width: 100%">
                <map :name="item.id" :id="item.id">
                  <area shape="rect" :coords="area.coordinate" :href="area.href" v-for="area in item.areas">
                </map>
              </div>
            </div>
          </div>
        </div>
      </div>
    </article>
  </div>
</template>

<script>

  import header from '../header/header.vue'
  import { swiper, swiperSlide } from 'vue-awesome-swiper'
  export default {
    name: 'carrousel',
    data() {
      return {
        swiperOption: {
          // NotNextTick is a component's own property, and if notNextTick is set to true, the component will not instantiate the swiper through NextTick, which means you can get the swiper object the first time (if you need to use the get swiper object to do what Things, then this property must be true)
          // notNextTick是一个组件自有属性，如果notNextTick设置为true，组件则不会通过NextTick来实例化swiper，也就意味着你可以在第一时间获取到swiper对象，假如你需要刚加载遍使用获取swiper对象来做什么事，那么这个属性一定要是true
          notNextTick: true,
          // swiper configs 所有的配置同swiper官方api配置
          autoplay: 2000,
          loop:true,
          direction : 'horizontal',
          autoplayDisableOnInteraction: false,
          grabCursor : true,
          setWrapperSize :true,
          autoHeight: false,
          pagination : '.swiper-pagination',
          paginationClickable :true,
          prevButton:false,
          nextButton:false,
          scrollbar: false,
          mousewheelControl : true,
          observeParents:true,
          // if you need use plugins in the swiper, you can config in here like this
          // 如果自行设计了插件，那么插件的一些配置相关参数，也应该出现在这个对象中，如下debugger
          debugger: true,
          // swiper callbacks
          // swiper的各种回调函数也可以出现在这个对象中，和swiper官方一样
          /*onTransitionStart(swiper){
            console.log(swiper)
          },*/
          // more Swiper configs and callbacks...
          // ...
        },
        items: [
          {
            id: 'map0',
            height: '90px',
            image: 'http://i.lifevccdn.com/upload/combinationchart/b6b9a0221e3b47b7a92b36201272f9e6_d1242x0.jpg',
            areas: [
              {
                coordinate: '0,9,123,88',
                href: '/all'
              },
              {
                coordinate: '123,9,251,90',
                href: '/all'
              },
              {
                coordinate: '251,9,375,89',
                href: '/all'
              }
            ]
          },
          {
            id: 'map1',
            height: '150px',
            image: 'http://i.lifevccdn.com/upload/combinationchart/9518bc17021a40d28bffa8eb521f6878_d1242x0.jpg',
            areas: [
              {
                coordinate: '0,1,375,148',
                href: '/all'
              }
            ]
          },
          {
            id: 'map2',
            height: '925px',
            image: 'http://i.lifevccdn.com/upload/combinationchart/c8d8ca2a7c6b468f95faefd8eb3959c1_d1242x0.jpg',
            areas: [
              {
                coordinate: '0,64,375,231',
                href: '/all'
              },
              {
                coordinate: '0,240,375,407',
                href: '/all'
              },
              {
                coordinate: '0,407,375,573',
                href: '/all'
              },
              {
                coordinate: '0,573,123,749',
                href: '/all'
              },
              {
                coordinate: '123,573,251,749',
                href: '/all'
              },
              {
                coordinate: '251,573,375,749',
                href: '/all'
              },
              {
                coordinate: '0,749,123,925',
                href: '/all'
              },
              {
                coordinate: '123,749,251,925',
                href: '/all'
              },
              {
                coordinate: '251,749,375,925',
                href: '/all'
              },
            ]
          },
          {
            id: 'map3',
            height: '238px',
            image: 'http://i.lifevccdn.com/upload/combinationchart/7d75b0fe2e8244bdbad79f4b39f8b62f_d1242x0.jpg',
            areas: [
              {
                coordinate: '0,26,371,235',
                href: '/all'
              }
            ]
          },
          {
            id: 'map4',
            height: '310px',
            image: 'http://i.lifevccdn.com/upload/combinationchart/3cea975b99f9458198e9ed706af9b391_d1242x0.jpg',
            areas: [
              {
                coordinate: '3,46,86,158',
                href: '/all'
              },
              {
                coordinate: '93,46,191,164',
                href: '/all'
              },
              {
                coordinate: '191,46,281,164',
                href: '/all'
              },
              {
                coordinate: '285,46,371,164',
                href: '/all'
              },
              {
                coordinate: '3,170,90,294',
                href: '/all'
              },
              {
                coordinate: '93,170,183,294',
                href: '/all'
              },
              {
                coordinate: '187,170,281,294',
                href: '/all'
              },
              {
                coordinate: '281,170,375,294',
                href: '/all'
              }
            ]
          },
          {
            id: 'map5',
            height: '100px',
            image: 'http://i.lifevccdn.com/upload/combinationchart/fdbd35036c1c485b975a85ff7572708b_d1242x0.jpg',
            areas: [
              {
                coordinate: '0,2,375,101',
                href: '/all'
              }
            ]
          },
          {
            id: 'map6',
            height: '689px',
            image: 'http://i.lifevccdn.com/upload/combinationchart/3da3d66f3c934a1285dd686cb28a1c90_d1242x0.jpg',
            areas: [
              {
                coordinate: '0,0,375,151',
                href: '/all'
              },
              {
                coordinate: '3,158,168,330',
                href: '/all'
              },
              {
                coordinate: '187,158,367,330',
                href: '/all'
              },
              {
                coordinate: '3,337,180,509',
                href: '/all'
              },
              {
                coordinate: '183,337,367,509',
                href: '/all'
              },{
                coordinate: '3,516,180,682',
                href: '/all'
              },{
                coordinate: '187,516,367,675',
                href: '/all'
              }
            ]
          },
          {
            id: 'map7',
            height: '689px',
            image: 'http://i.lifevccdn.com/upload/combinationchart/2485cba0eb4a4dde8b7a606807698800_d1242x0.jpg',
            areas: [
              {
                coordinate: '0,0,375,151',
                href: '/all'
              },
              {
                coordinate: '7,165,183,330',
                href: '/all'
              },
              {
                coordinate: '191,158,371,330',
                href: '/all'
              },{
                coordinate: '7,330,183,503',
                href: '/all'
              },{
                coordinate: '191,330,367,496',
                href: '/all'
              },{
                coordinate: '7,503,183,675',
                href: '/all'
              },{
                coordinate: '187,503,367,675',
                href: '/all'
              }
            ]
          },
          {
            id: 'map8',
            height: '484px',
            image: 'http://i.lifevccdn.com/upload/combinationchart/1e3cea01343b4608853918c1e9e281de_d1242x0.jpg',
            areas: [
              {
                coordinate: '0,0,375,150',
                href: '/all'
              },
              {
                coordinate: '11,164,127,314',
                href: '/all'
              },
              {
                coordinate: '131,159,243,309',
                href: '/all'
              },
              {
                coordinate: '247,164,360,309',
                href: '/all'
              },
              {
                coordinate: '11,314,123,474',
                href: '/all'
              },
              {
                coordinate: '127,314,243,469',
                href: '/all'
              },
              {
                coordinate: '247,314,360,469',
                href: '/all'
              }
            ]
          },
          {
            id: 'map9',
            height: '689px',
            image: 'http://i.lifevccdn.com/upload/combinationchart/6d9ec06b24ef43a089ec173e9303fa09_d1242x0.jpg',
            areas: [
              {
                coordinate: '0,0,375,151',
                href: '/all'
              },
              {
                coordinate: '11,158,183,330',
                href: '/all'
              },
              {
                coordinate: '187,158,371,337',
                href: '/all'
              },
              {
                coordinate: '11,330,180,503',
                href: '/all'
              },
              {
                coordinate: '183,330,371,503',
                href: '/all'
              },
              {
                coordinate: '7,503,176,675',
                href: '/all'
              },
              {
                coordinate: '183,503,367,675',
                href: '/all'
              }
            ]
          },
          {
            id: 'map10',
            height: '689px',
            image: 'http://i.lifevccdn.com/upload/combinationchart/d38c4504d1ae4d1bac0257b52cef4fdb_d1242x0.jpg',
            areas: [
              {
                coordinate: '0,0,375,151',
                href: '/all'
              },
              {
                coordinate: '11,158,183,330',
                href: '/all'
              },
              {
                coordinate: '187,158,371,337',
                href: '/all'
              },
              {
                coordinate: '11,330,180,503',
                href: '/all'
              },
              {
                coordinate: '183,330,371,503',
                href: '/all'
              },
              {
                coordinate: '7,503,176,675',
                href: '/all'
              },
              {
                coordinate: '183,503,367,675',
                href: '/all'
              }
            ]
          },
          {
            id: 'map11',
            height: '484px',
            image: 'http://i.lifevccdn.com/upload/combinationchart/35f9e6158c1b422b916b3b0a69d156a9_d1242x0.jpg',
            areas: [
              {
                coordinate: '0,0,375,150',
                href: '/all'
              },
              {
                coordinate: '11,164,127,314',
                href: '/all'
              },
              {
                coordinate: '131,159,243,309',
                href: '/all'
              },
              {
                coordinate: '247,164,360,309',
                href: '/all'
              },
              {
                coordinate: '11,314,123,474',
                href: '/all'
              },
              {
                coordinate: '131,314,243,469',
                href: '/all'
              },
              {
                coordinate: '247,314,360,469',
                href: '/all'
              }
            ]
          },
          {
            id: 'map12',
            height: '101px',
            image: 'http://i.lifevccdn.com/upload/combinationchart/69410b3ad32e4f6ea1d49262902b7c59_d1242x0.jpg',
            areas: [
              {
                coordinate: '0,2,375,99',
                href: '/all'
              }
            ]
          },
          {
            id: 'map13',
            height: '190px',
            image: 'http://i.lifevccdn.com/upload/combinationchart/c67db6265fb94762998bf0eb82376249_d1242x0.jpg',
            areas: [
              {
                coordinate: '0,1,375,188',
                href: '/all'
              }
            ]
          },
        ]
      }
    },
    // you can find current swiper instance object like this, while the notNextTick property value must be true
    // 如果你需要得到当前的swiper对象来做一些事情，你可以像下面这样定义一个方法属性来获取当前的swiper对象，同时notNextTick必须为true
    computed: {
      swiper() {
        return this.$refs.mySwiper.swiper
      }
    },
    mounted() {
      // you can use current swiper instance object to do something(swiper methods)
      // 然后你就可以使用当前上下文内的swiper对象去做你想做的事了
      // console.log('this is current swiper instance object', this.swiper)
      this.swiper.slideTo(2, 1000, false)
    },
    components: {
      swiper,
      swiperSlide,
      'el-header': header
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus">
  article
    width: 100%
    margin: 0 auto
    padding-bottom: 48px
    color: #2e2e2e

  .home-body
    margin-top 98px
    .mint-loadmore
      overflow hidden
      .mint-loadmore-content
        //1transform translate3d(0, 0, 0)
        .mint-loadmore-top
          margin-top: -50px
          text-align: center
          height: 50px
          line-height: 50px
          .mint-loadmore-text
            vertical-align: middle
        .autoPlay
          .swiper-wrapper
            img
              width 100%
          .swiper-pagination
            .swiper-pagination-bullet-active
              background-color: #89be48
        .item-combo
          margin-bottom 5px
</style>
