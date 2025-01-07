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
            viewer.perspectiveControls.stopListenToKeyEvents();
            viewer.orthographicControls.stopListenToKeyEvents();
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
          <el-col :xs="16" :sm="21" style="margin: 0px auto;">
            <div id="gs" class="gs-container"></div>
          </el-col>
        </el-col>
      </el-row>
    </div>
  </template>


<style>

.gs-container {
  width: 100%;
  aspect-ratio: 16 / 9;
}

.spinnerPrimary0 {
  display: none !important;
}

.spinnerOuterContainer0 {
  height: 100% !important;
  margin: 0 auto !important;
  top: 0 !important;
  left: 0 !important;
}

.spinnerContainerPrimary0 {
  padding-top: 0% !important;
  position: relative !important;
  transform: none !important;
  width: fit-content !important;
  margin: 0 auto !important;
  left: 0 !important;
  padding: 10px 20px !important;
}

.messageContainerPrimary0 {
  padding-top: 0% !important;
}

</style>
