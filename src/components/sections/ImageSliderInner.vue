<script lang="ts" setup>
import { VueCompareImage } from 'vue3-compare-image';

const inputImagePath = './image_inner/line.jpg';
const outputImagePath = './image_inner/real.jpg';
</script>

<template>
  <div>
    <el-divider />

    <el-row justify="center">
      <h1 class="section-title">Image Inner Comparison</h1>
    </el-row>

    <el-row justify="center">
        <el-col :xs="24" :sm="20" :md="16" :lg="12" :xl="12">
            <el-row style="margin-top: 20px;" >
                <VueCompareImage 
                    :left-image="inputImagePath" 
                    :right-image="outputImagePath"
                    :hover="true"
                />
            </el-row>
        </el-col>
    </el-row>

  </div>
</template>

<style scoped>

</style>
