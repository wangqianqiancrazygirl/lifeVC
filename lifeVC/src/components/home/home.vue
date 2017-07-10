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
            <div>
              <div class="swiper-container">
                <div class="carousel-wrap" id="carousel">
                  <transition-group tag="ul" class='slide-ul' name="list">
                    <li v-for="(list,index) in slideList" :key="index" v-show="index===currentIndex" @mouseenter="stop"
                        @mouseleave="go">
                      <a :href="list.clickUrl">
                        <img :src="list.image" :alt="list.desc">
                      </a>
                    </li>
                  </transition-group>
                  <div class="carousel-items">
                  <span v-for="(item,index) in slideList.length" :class="{'active':index===currentIndex}"
                        @mouseover="change(index)"></span>
                  </div>
                </div>
              </div>
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
  export default {
    data () {
      return {
        slideList: [
          {
            "clickUrl": "#",
            "desc": "nhwc",
            "image": "http://i.lifevccdn.com/upload/IndexBanner/85f5aea681ab4e98b72f1d59b9a5b073_d1242x0.jpg"
          },
          {
            "clickUrl": "#",
            "desc": "hxrj",
            "image": "http://i.lifevccdn.com/upload/IndexBanner/09c6c6a15c2d48d19a03b473a7c3764a_d1242x0.jpg"
          },
          {
            "clickUrl": "#",
            "desc": "rsdh",
            "image": "http://i.lifevccdn.com/upload/IndexBanner/e234e5b64ab1456c9345dc8a4d604fb2_d1242x0.jpg"
          },
          {
            "clickUrl": "#",
            "desc": "nhwc",
            "image": "http://i.lifevccdn.com/upload/IndexBanner/b074f4f091d44569acdd9d001cd4e0b5_d1242x0.jpg"
          },
          {
            "clickUrl": "#",
            "desc": "hxrj",
            "image": "http://i.lifevccdn.com/upload/IndexBanner/924590309cb749fabf810a832a402984_d1242x0.jpg"
          },
          {
            "clickUrl": "#",
            "desc": "rsdh",
            "image": "http://i.lifevccdn.com/upload/IndexBanner/e0f30fd934134d28ad9c5c45f96c7045_d1242x0.jpg"
          }
        ],
        currentIndex: 0,
        timer: '',
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
    created () {
      this.$nextTick(() => {
        this.timer = setInterval(() => {
          this.autoPlay()
        }, 3000)
      })
    },
    methods: {
      go() {
        this.timer = setInterval(() => {
          this.autoPlay()
        }, 3000)
      },
      stop() {
        clearInterval(this.timer)
        this.timer = null
      },
      change(index) {
        this.currentIndex = index
      },
      autoPlay() {
        this.currentIndex++
        if (this.currentIndex > this.slideList.length - 1) {
          this.currentIndex = 0
        }
      }
    },
    components: {
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
        //transform translate3d(0, 0, 0)
        .mint-loadmore-top
          margin-top: -50px
          text-align: center
          height: 50px
          line-height: 50px
          .mint-loadmore-text
            vertical-align: middle
        .swiper-container
          height: 250px
          margin-left: auto
          margin-right: auto
          position: relative
          z-index: 1
          .carousel-wrap
            position: relative
            height: 250px
            width: 100%
            background-color: #fff
            .slide-ul
              width: 100%
              height: 100% /*&.list-enter-active
                transition: all 1s ease
                transform: translateX(0)
              &.list-leave-active
                transition: all 1s ease
                transform: translateX(-100%)
              &.list-enter
                transform: translateX(100%)
              &.list-leave
                transform: translateX(0)*/
              li
                position: absolute
                width: 100%
                height: 100%
                img
                  width: 375px
            .carousel-items
              position: absolute
              z-index: 2000
              top: 240px
              width: 100%
              margin: 0 auto
              text-align: center
              font-size: 0
              span
                display: inline-block
                height: 8px
                width: 8px
                border-radius 50%
                margin: 0 5px
                background-color: white
                cursor: pointer
              .active
                background-color: #89be48
        .item-combo
          margin-bottom 5px
</style>
