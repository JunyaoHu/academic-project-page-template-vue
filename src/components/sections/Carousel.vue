<script>
export default {
    data() {
    return {
        source_paths: [
        "./carousel/1.jpg",
        "./carousel/2.jpg",
        "./carousel/3.jpg",
        "./carousel/4.jpg",
        "./carousel/5.jpg",
      ],
    }
  }
}
</script>

<template>
  <div>
    <el-carousel height="auto" trigger="click" type="card" style="text-align: center">
      <el-carousel-item v-for="path in source_paths" style="height: 540px">
        <el-image :src="path"/>
      </el-carousel-item>
    </el-carousel>
  </div>
</template>
  
<style scoped>
.demonstration {
    color: var(--el-text-color-secondary);
}

.el-carousel__item h3 {
    color: #539af7;
    opacity: 0.75;
    line-height: 150px;
    margin: 0;
    text-align: center;
}

.el-carousel__item:nth-child(2n) {
    background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n + 1) {
    background-color: #d3dce6;
}
</style>
  