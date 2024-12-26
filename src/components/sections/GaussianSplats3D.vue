<script setup lang="ts">
import { onMounted } from 'vue';
import * as GaussianSplats3D from '@mkkellogg/gaussian-splats-3d';

onMounted(() => {
    const gs = document.getElementById('gs');
    if (gs) {
        const viewer = new GaussianSplats3D.Viewer({
            'rootElement': gs,
            'cameraUp': [0, -1, 0],
            'initialCameraPosition': [-2.13, -0.50, -4.63],
            'initialCameraLookAt': [-0.08, 0.89, -1.36],
            'sharedMemoryForWorkers': false,
        });
        viewer.addSplatScene('./3dgs/cotton-mirror.splat', {
            'splatAlphaRemovalThreshold': 5,
            'showLoadingUI': true,
            'position': [0, 1, -1],
            'rotation': [0, 0, 0, 1],
            'scale': [0.18, 0.18, 0.18]
        })
        .then(() => {
            viewer.start();
        });
    }
});
</script>

<template>
    <div>
      <el-divider />
  
      <el-row justify="center">
        <h1 class="section-title">3DGS Model</h1>
      </el-row>
  
      <el-row justify="center">
        <el-col :xs="24" :sm="20" :md="16" :lg="12" :xl="12">
          <p>
          Thanks to
          <a href="https://github.com/mkkellogg/GaussianSplats3D" target="_blank">GaussianSplats3D</a>,
          we can visualize 3DGS models here.
          </p>
          <el-row justify="center">
            <el-col :xs="20" :sm="24" >
              <div id="gs"></div>
            </el-col>
          </el-row>
          
        </el-col>
      </el-row>
    </div>
  </template>


<style scoped>

/* 摘要文字居中 */
p {
  text-align: justify;
} 

/* 链接颜色装饰 */
a {
  color: #3273dc;
  text-decoration: none;
}

/* 鼠标焦点悬浮在链接上的颜色装饰 */
a:hover {
  color: #848484;
  border-bottom: dotted;
}

#gs {
    height: 350px;
}

</style>