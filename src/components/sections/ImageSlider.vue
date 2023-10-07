<script>
export default {
  data() {
    return {
      sliderValue: 0, // 滑块的值
      inputImagePath:  './image_slider/huaqiang/input/', // 图片存放路径
      outputImagePath: './image_slider/huaqiang/output/',
      minValue: 0,
      maxValue: 9,
    };
  },
  computed: {
    // 根据滑块的值构建图片的资源路径
    inputImageSrc() {
      return `${this.inputImagePath}${this.sliderValue}.png`;
    },
    outputImageSrc() {
      return `${this.outputImagePath}${this.sliderValue}.png`;
    },
  },
};
</script>

<template>
  <div class="bg">
    <el-row>
      <h1 class="title1">Image Slider</h1>
    </el-row>
    <el-row>
      <el-col :xs="20" :sm="20" :md="16" :lg="12" :xl="12">
        <el-row justify="space-evenly">
            <el-col :xs="10" :sm="10" :md="8" :lg="6" :xl="6">
                <div class="demo-image">
                    <div class="block">
                        <el-image :src="inputImageSrc" fit="scale-down"/>
                        <span class="demonstration">input</span>
                    </div>
                </div>
            </el-col>
            <el-col :xs="10" :sm="10" :md="8" :lg="6" :xl="6">
                <div class="demo-image">
                    <div class="block">
                        <el-image :src="outputImageSrc" fit="scale-down"/>
                        <span class="demonstration">output</span>
                    </div>
                </div>
            </el-col>
        </el-row>
    </el-col>
    </el-row>
    <el-row>
      <el-col :xs="20" :sm="20" :md="16" :lg="12" :xl="12">
        <div class="slider-demo-block">
            <el-slider v-model="sliderValue" show-input :min="minValue" :max="maxValue" />
        </div>
      </el-col>
    </el-row>
  </div>
</template>

<style scoped>
.slider-demo-block {
  display: flex;
  align-items: center;
}
.slider-demo-block .el-slider {
  margin-top: 0;
  margin-left: 12px;
  margin-bottom: 15px;
}

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
.demo-image .demonstration {
  display: block;
  color: var(--el-text-color-secondary);
}
</style>