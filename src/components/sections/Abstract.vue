<script>

export default {
  data() {
    return {
      abstract: "Aute amet minim mollit nisi adipisicing cupidatat. Duis sit tempor consequat ea nisi qui consequat deserunt. Officia duis sit mollit dolor officia occaecat. Minim aute excepteur nostrud adipisicing magna nisi amet. Laborum aliqua ut ex cillum qui ipsum tempor officia sunt. Reprehenderit est ex sit fugiat laborum reprehenderit proident deserunt sint pariatur cillum voluptate irure. Voluptate laboris velit veniam exercitation sunt eiusmod occaecat velit fugiat ad."
    }
  }
}
</script>

<template>
  <div>
    <el-divider />

    <el-row justify="center">
      <h1 class="section-title">Abstract</h1>
    </el-row>

    <el-row justify="center">
      <el-col :xs="24" :sm="20" :md="16" :lg="12" :xl="12">
        <p>{{ abstract }}</p>
      </el-col>
    </el-row>
  </div>
</template>

<style scoped>

/* 摘要文字居中 */
p {
  text-align: justify;
} 

</style>