<script lang="ts" setup>
import { vue3dLoader } from "vue-3d-loader";

</script>

<template>
  <div>
    <el-divider />

    <el-row justify="center">
      <h1 class="section-title">3D Model</h1>
    </el-row>

    <el-row justify="center">
      <el-col :xs="24" :sm="20" :md="16" :lg="12" :xl="12">
        <p>
        Thanks to
        <a href="https://github.com/king2088/vue-3d-loader" target="_blank">vue-3d-loader</a>,
        we can visualize these 3D models here. It supports dae, fbx, gltf(glb), obj, ply, stl models.
        </p>
        <el-row justify="space-evenly">
          <el-col :xs="16" :sm="10" >
            <div class="threed-container">
              <vue3dLoader
              filePath="./model3d/obj/male02.obj"
              mtlPath="./model3d/obj/male02.mtl"
              outputEncoding="sRGB"
              :cameraPosition="{ x: 0, y: 0, z: 300 }"
              :scale="{ x: 1, y: 1, z: 1 }"
              :position="{ x: 0, y: 0, z: 0 }"
              :rotation="{ x: 0, y: 0, z: 0 }"
              :enableDamping="true"
              :dampingFactor="0.05"
              :backgroundColor="'#f2f2f2'"
            />
            </div>
          </el-col>
          <el-col :xs="16" :sm="10" >
            <vue3dLoader
              filePath="./model3d/ply/Lucy100k.ply"
              :cameraPosition="{ x: 100, y: 200, z: 3000 }"
              :scale="{ x: 1, y: 1, z: 1 }"
              :position="{ x: 100, y: 100, z: 100 }"
              :rotation="{ x: 0, y: 3, z: 0 }"
              :enableDamping="true"
              :dampingFactor="0.05"
              :backgroundColor="0xeeeeee"
            ></vue3dLoader>
          </el-col>
        </el-row>
        
        
      </el-col>
    </el-row>
  </div>
</template>

<style>
.viewer-canvas {
  width: 100% !important;
  height: auto !important;
  aspect-ratio: 1 / 1 !important;
}
</style>