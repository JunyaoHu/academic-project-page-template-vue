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
      <el-col :xs="24" :sm="20" :md="16" :lg="12" :xl="10" >
        <el-container id="video-container">
          <iframe src="//player.bilibili.com/player.html?isOutside=true&aid=802517980&bvid=BV1qy4y1x7VV&cid=325180260&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>
        </el-container>
      </el-col>
    </el-row>

  </div>
</template>

<style scoped>

#video-container{
  margin: 15px 0px 0px 0px;
}

iframe {
  aspect-ratio: 16 / 9;
  height: 100%;
  width: 100%;
}

</style>