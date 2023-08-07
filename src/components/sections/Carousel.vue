<script>
import { Swiper, SwiperSlide} from 'swiper/vue';
import { Navigation, Pagination, Autoplay} from 'swiper/modules';
import 'swiper/css/bundle';

export default {
  components: {
      Swiper,
      SwiperSlide,
      Navigation,
      Pagination,
      Autoplay,
    },
  data() {
    return {
        modules: [
          Navigation,
          Pagination,
          Autoplay,
        ],
        image_paths: [
        "./carousel/1.jpg",
        "./carousel/2.jpg",
        "./carousel/3.jpg",
        "./carousel/4.jpg",
        "./carousel/5.jpg",
        "./carousel/6.jpg",
      ],
    }
  }
}
</script>

<template>
  <div>

    <swiper
      :loop="true"
      :slidesPerView="1"
      :breakpoints="{
        600: {
          slidesPerView: 2,
        },
        800: {
          slidesPerView: 3,
        },
      }"
      :modules="modules"
      :navigation="{ }"
      :pagination="{ 
        clickable:true, 
        type:'bullets' 
      }"
      :autoplay="{ 
        delay:5000,
        disableOnInteraction:false,
        pauseOnMouseEnter:true,
      }"
      >
      <swiper-slide v-for="path in image_paths">
        <el-image :src="path"/>
      </swiper-slide>
    </swiper>

  </div>
</template>
  
<style>

.swiper {
  --swiper-theme-color: white;/* 设置Swiper风格 */
}

</style>
  