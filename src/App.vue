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
  <!-- <div class="common-layout"> -->
  <div>
    <el-container>
      <el-header><Header/></el-header>
      <el-main><Main/></el-main>
      <el-footer><Footer/></el-footer>
    </el-container>

    <!-- 回到顶部 -->
    <el-backtop :right="40" :bottom="40" />
  </div>
</template>

<style>
.el-header {
  padding: 0px;
}

.el-footer {
  padding: 0px;
}
</style>