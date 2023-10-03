<script>

import Header from './components/Header.vue'
import Main from './components/Main.vue'
import Footer from './components/Footer.vue'

export default {
  
  components: {
    Header,
    Main,
    Footer,
  }
}
</script>

<template>
  <div class="common-layout">
    
    <el-container>
      <el-header><Header/></el-header>
      <el-main><Main/></el-main>
      <el-footer><Footer/></el-footer>
    </el-container>

    <el-backtop :right="40" :bottom="40" />
  </div>
</template>

<style>

</style>