<template>
  <div v-swiper:mySwiper="swiperOption">
    <div class="swiper-wrapper wrap">
      <div class="swiper-slide slideItem" :key="banner" v-for="banner in banners">
        <img :src="banner">
      </div>
    </div>
    <!--分页器-->
    <div class="swiper-pagination" slot="pagination"></div>
    <!--左右箭头-->
    <div class="swiper-button-prev" slot="button-prev"></div> 
    <div class="swiper-button-next" slot="button-next"></div> 
  </div>
</template>

<script>
  export default {
    name: 'HelloWorld',
    data () {
      return {
        banners: [ 
          require("../assets/m1.jpg"),
          require("../assets/m2.jpg"),
          require("../assets/m3.jpg"),
          require("../assets/m4.jpg"),
          require("../assets/m5.jpg"),
          require("../assets/m6.jpg"),  
        ],
        swiperOption: {
          pagination: {
            el: '.swiper-pagination',
            //控住分页器的顺序切换
            clickable: true,
          },
          navigation: {
            prevEl: '.swiper-button-prev',
            nextEl: '.swiper-button-next'
          },
          //自动轮播
          autoplay: {
            delay: 1500,
            //当用户滑动图片后继续自动轮播
            disableOnInteraction: false,
          },
          loop: true,
           // 一行显示slider的个数
          slidesPerView: 2,
        
          // 定义slides的数量多少为一组
           slidesPerGroup: 2,
        }
      }
    },
  }
</script>

<style scoped>
.swiper-container {
  width: 1300px;
  height: 300px;
}
.slideItem {
  box-sizing: border-box;
  padding: 10px;
}
.slideItem img{
  width: 100%;
  height: 100%;
  /* object-fit: cover; */
}
.swiper-wrapper{
  transition-timing-function:linear !important;
}
</style>