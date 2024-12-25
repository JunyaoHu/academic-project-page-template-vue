<script>
import Title from './sections/Title.vue'
import Abstract from './sections/Abstract.vue'
import BibTeX from './sections/BibTeX.vue'
import Carousel from './sections/Carousel.vue'
import Video from './sections/Video.vue'
import ImageSlider from './sections/ImageSlider.vue'
import Echart from './sections/Echart.vue'
import Table from './sections/Table.vue'
import Collapse from './sections/Collapse.vue'
import SeletionForComparison from './sections/SeletionForComparison.vue'
import Comment from './sections/Comment.vue'
import Latex from './sections/Latex.vue'
import Model3D from './sections/Model3D.vue'

export default {
  components: {
    Title,
    Abstract,
    BibTeX,
    Carousel,
    Video,
    ImageSlider,
    Echart,
    Collapse,
    Table,
    SeletionForComparison,
    Comment,
    Latex,
    Model3D
  }
}
</script>

<template>
  <Title/>
  <Carousel/>
  <Video/>
  <Abstract/>
  <Latex/>
  <Echart/>
  <Model3D/>
  <Table/>
  <Collapse/>
  <SeletionForComparison/>
  <ImageSlider/>
  <BibTeX/>
  <Comment/>
</template>