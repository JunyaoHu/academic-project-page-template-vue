<script>

import Title from './sections/Title.vue'
import Abstract from './sections/Abstract.vue'
import BibTeX from './sections/BibTeX.vue'

export default {
  components: {
    Title,
    Abstract,
    BibTeX,
  }
}
</script>

<template>
    <Title/>
    <Abstract/>
    <BibTeX/>
</template>