<script>
export default {
  data() {
    return {
      sliderValue: 0, // 滑块的值
      inputImageRootPath:  './image_slider/huaqiang/input/', // 图片存放路径
      outputImageRootPath: './image_slider/huaqiang/output/',
      inputImagePath: '',
      outputImagePath: '',
      inputLoading: true,
      outputLoading: true,
      minValue: 0,
      maxValue: 9,
    };
  },
  beforeMount() {
    // 在组件挂载之前预加载第一张图片
    this.loadImage(this.sliderValue, this.inputImageRootPath, 'input');
    this.loadImage(this.sliderValue, this.outputImageRootPath, 'output');
  },
  methods: {
    handleChange(value) {
      // 当滑块的值改变时，加载对应的图片
      this.loadImage(value, this.inputImageRootPath, 'input');
      this.loadImage(value, this.outputImageRootPath, 'output');
    },
    loadImage(value, path, type) {
      // 构建图片路径
      if (type == 'input') {
          this.inputLoading = true;
      } else {
          this.outputLoading = true;
      }
      const imagePath = `${path}${value}.png`;
      // 创建一个新的Image对象用于预加载
      const image = new Image();
      image.src = imagePath;
      // 监听图片加载完成事件
      image.onload = () => {
          // 图片加载完成后，更新当前图片路径
          if (type == 'input') {
            this.inputImagePath = imagePath;
            console.log(this.inputImagePath);
            this.inputLoading = false;
          } else {
            this.outputImagePath = imagePath;
            console.log(this.outputImagePath);
            this.outputLoading = false;
          }
      };
    },
  },
};
</script>

<template>
  <div class="bg">
  <el-row>
    <h1 class="title1">Image Slider</h1>
  </el-row>
  <div>
      <label style="margin-right: 16px">Switch Loading</label>
      <el-switch v-model="inputLoading" />
  </div>
  <el-row>
    <el-col>
      <el-row justify="space-evenly">
        <el-col :lg="10" :xl="6">
          <div class="demo-image">
            <div class="block">
              <el-skeleton
              style="width: 100%"
              :loading="inputLoading"
              animated
              :throttle="1000"
              >
                <template #template>
                  <el-skeleton-item variant="image" style="width: 100%; height: 100%" />
                </template>
                <template #default>
                  <el-image :src="inputImagePath" fit="scale-down"/>
                </template>
              </el-skeleton>
              <span class="demonstration">input: {{ inputImagePath }}</span>
            </div>
          </div>
        </el-col>
        <el-col :lg="10" :xl="6">
          <div class="demo-image">
            <div class="block">
              <el-skeleton
              style="width: 100%"
              :loading="outputLoading"
              animated
              :throttle="1000"
              >
                <template #template>
                  <el-skeleton-item variant="image" style="width: 100%; height: 100%" />
                </template>
                <template #default>
                  <el-image :src="outputImagePath" fit="scale-down"/>
                </template>
              </el-skeleton>
              <span class="demonstration">output: {{ outputImagePath }}</span>
            </div>
          </div>
        </el-col>
      </el-row>
    </el-col>
  </el-row>
  <el-row>
    <el-col :xs="20" :sm="20" :md="16" :lg="12" :xl="12">
    <div class="slider-demo-block">
      <el-slider v-model="sliderValue" :min="minValue" :max="maxValue" @input="handleChange"/>
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

<style>
.el-slider__runway {
  background-color: #c6c6c6;
}
</style>