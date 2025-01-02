<script setup>
import { ref, onMounted } from 'vue';

const NUM_INTERP_FRAMES = 10;
const inputImagePaths = [];
const outputImagePaths = [];
const inputImageRootPath = './image_slider/huaqiang/input/';
const outputImageRootPath = './image_slider/huaqiang/output/';
const minValue = 0;
const maxValue = 9;
let inputImagePath = ref("");
let outputImagePath = ref("");
let sliderValue = ref(0);
let isLoading = ref(true);

const preloadInterpolationImages = () => {
  const promises = [];

  for (var i = 0; i < NUM_INTERP_FRAMES; i++) {
    var inputPath = inputImageRootPath + String(i) + '.png';
    const inputImg = new Image();
    inputImagePaths[i] = inputImg;
    const inputPromise = new Promise((resolve) => {
      inputImg.onload = resolve;
    });
    inputImg.src = inputPath;
    promises.push(inputPromise);

    var outputPath = outputImageRootPath + String(i) + '.png';
    const outputImg = new Image();
    outputImagePaths[i] = outputImg;
    const outputPromise = new Promise((resolve) => {
        outputImg.onload = resolve;
    });
    outputImg.src = outputPath;
    promises.push(outputPromise);
  }

  return Promise.all(promises).then(() => {
    isLoading.value = false;
    console.log("preloadInterpolationImages finished");
  });
}

onMounted(() => {
    preloadInterpolationImages();
    handleChange(0);
});

const handleChange = (value) => {
  // 当滑块的值改变时，加载对应的图片
  inputImagePath.value = inputImagePaths[value].src;
  outputImagePath.value = outputImagePaths[value].src;
};

</script>

<template>
  <div>
    <el-divider />

    <el-row justify="center">
      <h1 class="section-title">Qualitative Results</h1>
    </el-row>

    <el-row justify="center">
      <el-col>
        <el-row justify="center" :gutter="20">
          <el-col :xs="12" :sm="10" :md="8" :lg="6" :xl="6" >
            <div class="demo-image">
              <div class="block">
                <!-- 预加载骨架 -->
                <el-skeleton
                style="width: 100%"
                :loading="isLoading"
                animated
                :throttle="1000">
                  <!-- 骨架模板 -->
                  <template #template>
                    <el-skeleton-item variant="image" style="width: 100%; height: 100%" />
                  </template>
                  <!-- 实际显示图像内容 -->
                  <template #default>
                    <img :src="inputImagePath" style="width: 100%; object-fit: contain;">
                  </template>
                </el-skeleton>
                <!-- 图片路径 -->
                <span class="demonstration">input: {{ inputImagePath }}</span>
              </div>
            </div>
          </el-col>

          <el-col :xs="12" :sm="10" :md="8" :lg="6" :xl="6" >
            <div class="demo-image">
              <div class="block">
                <!-- 预加载骨架 -->
                <el-skeleton
                style="width: 100%"
                :loading="isLoading"
                animated
                :throttle="1000">
                  <!-- 骨架模板 -->
                  <template #template>
                    <el-skeleton-item variant="image" style="width: 100%; height: 100%" />
                  </template>
                  <!-- 实际显示图像内容 -->
                  <template #default>
                    <img :src="outputImagePath" style="width: 100%; object-fit: contain;">
                  </template>
                </el-skeleton>
                <!-- 图片路径 -->
                <span class="demonstration">output: {{ outputImagePath }}</span>
              </div>
            </div>
          </el-col>
        </el-row>
      </el-col>
    </el-row>

    <!-- 滑块控制 -->
    <el-row justify="center">
      <el-col :span="12">
          <el-slider v-model="sliderValue" :min="minValue" :max="maxValue" @input="handleChange"/>
      </el-col>
    </el-row>

  </div>
</template>

<style scoped>

/* 滑块 */
.el-slider {
  margin: 15px 0;
}

/* 路径文字居中 */
.demo-image .block {
  padding: 20px 0 0 0;
  text-align: center;
  border-right: solid 1px var(--el-border-color);
  display: inline-block;
  width: 100%;
  box-sizing: border-box;
  vertical-align: top;
}

.demo-image .block:last-child {
  border-right: none;
}

/* 路径文字颜色 */
.demo-image .demonstration {
  padding-top: 10px;
  display: block;
  color: var(--el-text-color-secondary);
  word-wrap: break-word;
}

/* 滑块背景颜色 */
.el-slider__runway {
  background-color: #c6c6c6;
}
</style>
