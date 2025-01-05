<script setup>
import { ref, onMounted } from 'vue';

const imageSeletorPaths = [
  "./image_selector/input/486.png",
  "./image_selector/input/mmk.png",
  "./image_selector/input/nina.png",
  "./image_selector/input/rupa.png",
  "./image_selector/input/tomo.png"
];

const outputImagesPathsStr = [
  "./image_selector/output/486_model.jpg",
  "./image_selector/output/mmk_model.jpg",
  "./image_selector/output/nina_model.jpg",
  "./image_selector/output/rupa_model.jpg",
  "./image_selector/output/tomo_model.jpg"
];

const outputImagesPaths = [];

let outputImagePath = ref("");
let indexSelected = ref(0);
let isLoading = ref(true);

const preloadImageSelector = () => {
  const promises = [];
      
  for (let i = 0; i < outputImagesPathsStr.length; i++) {
    const outputImg = new Image();
    outputImagesPaths[i] = outputImg;
    const outputPromise = new Promise((resolve) => {
        outputImg.onload = resolve;
    });
    outputImg.src = outputImagesPathsStr[i];
    promises.push(outputPromise);
  }

  return Promise.all(promises).then(() => {
    isLoading.value = false;
    console.log("preloadImageSelector finished");
  });
}

onMounted(() => {
    preloadImageSelector();
    handleChange(0);
});

const handleChange = (value) => {
  indexSelected.value = value;
  outputImagePath.value = outputImagesPaths[value].src;
};

</script>

<template>
  <div>
    <el-divider />

    <el-row justify="center">
      <h1 class="section-title">Image Selector</h1>
    </el-row>

    <el-row justify="center">
      <el-col :xs="24" :sm="20" :md="16" :lg="12" :xl="12">
        <el-row justify="space-evenly" style="margin-top: 20px;">
          <el-col :span="4" v-for="(imageSeletorPath, index) in imageSeletorPaths" :key="index">
            <el-image 
              class="image" 
              :src="imageSeletorPath" style="aspect-ratio: 1;" 
              fit="scale-down" 
              @click="handleChange(index)"
              :class="{ 'selected-image': indexSelected === index, 'unselected-image': indexSelected !== index }"
            />
          </el-col>
          <el-row justify="center" style="margin-top: 10px;">
            <el-col :span="12">
              <el-skeleton
                style="width: 100%"
                :loading="isLoading"
                animated
                :throttle="1000">
                <template #template>
                  <el-skeleton-item variant="image" style="width: 100%; height: 100%" />
                </template>
                <template #default>
                  <img :src="outputImagePath" style="width: 100%; object-fit: contain;">
                </template>
              </el-skeleton>
            </el-col>
          </el-row>
        </el-row>
      </el-col>
    </el-row>
  </div>
</template>

<style scoped>

.image:hover{
  transition: none;
  box-shadow: 0px 0px 6px 0px #aaaaaa;
}

.selected-image{
  transition: 0.5s ease;
  box-shadow: 0px 0px 6px 0px #aaaaaa;
}


/* 未选中图像的样式，颜色变灰 */
.unselected-image {
  transition: 0.5s ease;
  opacity: 0.4;
}

</style>