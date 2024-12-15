<script>

export default {
  data() {
    return {
      value1: '',
      value2: '',
      comparison1ImageRootPath: '',
      comparison2ImageRootPath: '',
      comparisonImageRootPath: './image_comparison/',
      comparison1Loading: true,
      comparison2Loading: true,
      options: [
        'bottle',
        'box',
        'clip',
        'cup',
        'duck',
        'flim',
        'glass',
        'toy'
      ],
    }
  },
  beforeMount() {
    // 在组件挂载之前预加载第一张图片
    this.handleChange1(this.options[0]);
    this.handleChange2(this.options[1]);
  },
  methods: {
    handleChange1(value) {
      this.loadImage1(value);
    },
    handleChange2(value) {
      this.loadImage2(value);
    },

    loadImage1(value) {
      this.comparison1Loading = true;
      const imagePath = `${this.comparisonImageRootPath}${value}.png`;
      // 创建一个新的Image对象用于预加载
      const image = new Image();
      image.src = imagePath;
      // 监听图片加载完成事件
      image.onload = () => {
          this.comparison1ImageRootPath = imagePath;
          // 图片加载完成后，更新当前图片路径
          this.comparison1Loading = false;
      };
    },

    loadImage2(value) {
      this.comparison2Loading = true;
      const imagePath = `${this.comparisonImageRootPath}${value}.png`;
      // 创建一个新的Image对象用于预加载
      const image = new Image();
      image.src = imagePath;
      // 监听图片加载完成事件
      image.onload = () => {
          this.comparison2ImageRootPath = imagePath;
          // 图片加载完成后，更新当前图片路径
          this.comparison2Loading = false;
      };
    },
  },
}
</script>

<template>
  <div>
    <el-divider />

    <el-row justify="center">
      <h1 class="section-title">Comparison</h1>
    </el-row>

    <el-row justify="center">
      <el-col >
        <el-row justify="center" :gutter="20">

          <el-col :xs="12" :sm="10" :md="8" :lg="6" :xl="6" >

            <div class="demo-image">
              <div class="block">
                <el-skeleton
                style="width: 100%"
                :loading="comparison1Loading"
                animated
                :throttle="1000"
                >
                  <template #template>
                    <el-skeleton-item variant="image" style="width: 100%; height: 100%" />
                  </template>
                  <template #default>
                    <el-image :src="comparison1ImageRootPath" style="width: 100%; height: 100%" fit="scale-down"/>
                  </template>
                </el-skeleton>
                <span class="demonstration">input: {{ comparison1ImageRootPath }}</span>
              </div>
            </div>

            <el-row justify="center">
                <el-select
                  class="select"
                  v-model="value1"
                  placeholder="Select"
                  size="large"
                  @change="handleChange1"
                >
                  <el-option
                    v-for="item in options"
                    :key="item"
                    :label="item"
                    :value="item"/>
                </el-select>
            </el-row>

          </el-col>

          <el-col :xs="12" :sm="10" :md="8" :lg="6" :xl="6" >
            
            <div class="demo-image">
              <div class="block">
                <el-skeleton
                style="width: 100%"
                :loading="comparison2Loading"
                animated
                :throttle="1000"
                >
                  <template #template>
                    <el-skeleton-item variant="image" style="width: 100%; height: 100%" />
                  </template>
                  <template #default>
                    <el-image :src="comparison2ImageRootPath" style="width: 100%; height: 100%" fit="scale-down"/>
                  </template>
                </el-skeleton>
                <span class="demonstration">input: {{ comparison2ImageRootPath }}</span>
              </div>
            </div>

            <el-row justify="center">
              <el-select
                class="select"
                v-model="value2"
                placeholder="Select"
                size="large"
                @change="handleChange2"
              >
                <el-option
                  v-for="item in options"
                  :key="item"
                  :label="item"
                  :value="item"/>
              </el-select>
            </el-row>
          </el-col>

        </el-row>
      </el-col>
    </el-row>

  </div>
</template>

<style scoped>

.select {
  padding-top: 10px;
  width: 200px;
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

</style>