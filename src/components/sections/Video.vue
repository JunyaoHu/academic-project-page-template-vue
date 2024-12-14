<script>

</script>

<template>
  <div>
    <el-divider />

    <el-row justify="center">
      <h1 class="section-title">Explainer Video</h1>
    </el-row>

    <!-- 每个网站的视频的iframe可能不一致，最好在这里手动调整 -->
    <el-row justify="center">
      <el-col :xs="24" :sm="24" :md="15" :lg="12" :xl="10">
        <iframe src="//player.bilibili.com/player.html?aid=802517980&bvid=BV1qy4y1x7VV" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>
      </el-col>
    </el-row>

  </div>
</template>

<style scoped>
@media screen{
iframe {
    position: center;
    width: 100%;
    height: 425px;
    padding: 20px 0; 
}}
</style>