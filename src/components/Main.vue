<script>

import Title from './sections/Title.vue'
import Abstract from './sections/Abstract.vue'
import BibTeX from './sections/BibTeX.vue'
import Carousel from './sections/Carousel.vue'
import Video from './sections/Video.vue'

export default {
  components: {
    Title,
    Abstract,
    BibTeX,
    Carousel,
    Video,
  }
}
</script>

<template>
    <Title/>
    <Video/>
    <Carousel/>
    <Abstract/>
    <BibTeX/>
</template>