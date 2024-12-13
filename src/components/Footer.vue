<script lang="ts" setup>
// 页脚需要的链接
const links = {
    Nerfies: "https://github.com/nerfies/nerfies.github.io",
    Vue: "https://cn.vuejs.org/",
    Vite: "https://cn.vitejs.dev/",
    ElementPlus: "https://element-plus.org/zh-CN/",
    template: "https://junyaohu.github.io/template/",
}
</script>

<template>
  <div class="bg">
    <el-row>
      <el-col>
          <p class="footer">
            This template is inspired by 
            <a :href="links.Nerfies">Nerfies</a>,<br/>

            powered by 
            <a :href="links.Vue">Vue</a>, 
            <a :href="links.Vite">Vite</a>, and
            <a :href="links.ElementPlus">Element Plus</a>.<br/>

            You can fork🛠️ / star✨/ PR📃 from <a :href="links.template">here</a>.
          </p>
      </el-col>
    </el-row>
  </div>
</template>

<style scoped>

/* 页脚背景 */
.bg {
  background-color: rgb(235, 235, 235);
}

/* 页脚文字 */
.footer {
  text-align: center;
  margin: 20px;
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