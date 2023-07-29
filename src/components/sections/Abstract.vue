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
  <div class="bg">
    <el-row>
      <h1 class="title1">Abstract</h1>
    </el-row>
    <el-row>
      <el-col :xs="20" :sm="20" :md="16" :lg="12" :xl="12">
        <p>{{ abstract }}</p>
      </el-col>
    </el-row>
  </div>
</template>

<style>

.title1 {
  font-family: "MyFont", Verdana, sans-serif;
  letter-spacing: 2px;
  font-size: 28px;
  text-align: center;
  margin-bottom: 0px;
}

.bg {
  background-color: rgb(235, 235, 235);
}

p {
  text-align: justify;
} 

</style>