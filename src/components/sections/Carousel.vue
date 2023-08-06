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
        source_paths: [
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
    <!-- <el-carousel height="540px" trigger="click" type="card" style="text-align: center">
      <el-carousel-item v-for="path in source_paths">
        <el-image :src="path"/>
      </el-carousel-item>
    </el-carousel> -->

    <swiper
      :loop="true"
      :modules="modules"
      :slides-per-view="3"
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
      <swiper-slide v-for="path in source_paths">
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
  