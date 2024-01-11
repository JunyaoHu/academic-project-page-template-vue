<script>
import Title from './sections/Title.vue'
import Abstract from './sections/Abstract.vue'
import BibTeX from './sections/BibTeX.vue'
import Carousel from './sections/Carousel.vue'
import Video from './sections/Video.vue'
import ImageSlider from './sections/ImageSlider.vue'
import Echart from './sections/Echart.vue'

export default {
  components: {
    Title,
    Abstract,
    BibTeX,
    Carousel,
    Video,
    ImageSlider,
    Echart,
  }
}
</script>

<template>
    <Title/>
    <Video/>
    <Carousel/>
    <Abstract/>
    <Echart/>
    <ImageSlider/>
    <BibTeX/>
</template>