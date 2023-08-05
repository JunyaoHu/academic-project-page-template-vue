<script>

import Title from './sections/Title.vue'
import Abstract from './sections/Abstract.vue'
import BibTeX from './sections/BibTeX.vue'
import Carousel from './sections/Carousel.vue'

export default {
  components: {
    Title,
    Abstract,
    BibTeX,
    Carousel,
  }
}
</script>

<template>
    <Title/>
    <Carousel/>
    <Abstract/>
    <BibTeX/>
</template>