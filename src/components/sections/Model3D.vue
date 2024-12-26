<script lang="ts" setup>
import { vue3dLoader } from "vue-3d-loader";
import { ref } from "vue";
const filePath = ref();
filePath.value = [
  "./model3d/fbx/Samba Dancing.fbx",
  "./model3d/collada/pump/pump.dae",
  "./model3d/ply/Lucy100k.ply",
];
const position = ref();
position.value = [
  { x: 100, y: 100, z: 100 },
  { x: 300, y: 300, z: 300 },
];
const rotation = ref();
rotation.value = [
  { x: 0, y: 0, z: 0 },
  { x: 10, y: 1, z: 1 },
];
const scale = ref();
scale.value = [
  { x: 5, y: 5, z: 5 },
  { x: 3, y: 3, z: 3 },
];
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
        <el-row justify="center">
          <el-col :xs="20" :sm="12" >
            <vue3dLoader
              filePath="./model3d/collada/stormtrooper/stormtrooper.dae"
              :cameraPosition="{ x: -8, y: 10, z: -10 }"
              :height="350"
              :enableDamping="true"
              :dampingFactor="0.05"
              :backgroundColor="0xccddff"
            />
          </el-col>
          <el-col :xs="20" :sm="12" >
            <vue3dLoader
              :filePath="filePath"
              :scale="scale"
              :position="position"
              :rotation="rotation"
              :cameraPosition="{ x: 100, y: 200, z: 3000 }"
              :parallelLoad="true"
              :height="350"
              :backgroundColor="0xeeeeee"
            ></vue3dLoader>
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

</style>