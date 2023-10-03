<script>

</script>

<template>
  <div class="bg">
    
    <el-row>
      <h1 class="title1">Explanatory Video</h1>
    </el-row>

    <el-row justify="space-evenly">
      <el-col>
        <el-col :xs="20" :sm="20" :md="10" :lg="10" :xl="5">
            <iframe src="//player.bilibili.com/player.html?aid=802517980&bvid=BV1qy4y1x7VV&cid=325180260&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>
        </el-col>
        <el-col :xs="20" :sm="20" :md="10" :lg="10" :xl="5">
            <iframe src="https://www.youtube.com/embed/1kE_VJgM4u8?si=JZ_XoMOZNfVG1lAF" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
        </el-col>
      </el-col>
    </el-row>

  </div>
</template>

<style>
@media screen{
iframe {
    position: center;
    width: 100%;
    height: 425px;
    padding: 20px 0; 
}}
</style>