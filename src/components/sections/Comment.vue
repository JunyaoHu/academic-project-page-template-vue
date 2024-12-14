<script>

// 评论配置
// Twikoo 支持腾讯云、Vercel、Railway 等多种平台部署
// Based on Tencent CloudBase
// See: https://twikoo.js.org

import { onMounted } from 'vue';

export default {
  // 这个钩子函数会在组件挂载到 DOM 之后被自动调用，
  // 非常适合用来初始化 Twikoo 评论插件。
  // 在mounted函数内部，通过调用twikoo.init方法，
  // 并传入相应的配置参数（如envId和el等，根据实际情况填写和配置可选参数）
  // 来完成 Twikoo 的初始化工作，使其能够正确地在页面上展示评论框
  // 并与后端环境交互（前提是后端环境已正确配置好对应的envId等相关设置）。
  setup() {
    onMounted(() => {
      twikoo.init({
        // 腾讯云环境填 envId；Vercel 环境填地址（https://xxx.vercel.app）
        envId: 'https://blog-comment-nvoz-8o7dxhfbd-junyaohus-projects.vercel.app', 
        // 容器元素
        el: '#twikoo', 
        // 环境地域，默认为 ap-shanghai，腾讯云环境填 ap-shanghai 或 ap-guangzhou；Vercel 环境不填
        region: '', 
        // 用于区分不同文章的自定义 js 路径，如果您的文章路径不是 location.pathname，需传此参数
        path: location.pathname,
        // 用于手动设定评论区语言，支持的语言列表 https://github.com/twikoojs/twikoo/blob/main/src/client/utils/i18n/index.js
        lang: 'zh-CN', 
      });
    });
  }
}
</script>

<template>
  <div>
    <el-divider />
    
    <el-row justify="center">
      <h1 class="section-title">💬 Comment</h1>
    </el-row>
    
    <el-row justify="center">
      <el-col :span="18" >
        <div id="twikoo"></div>
      </el-col>
    </el-row>
  </div>
</template>

<style>

/* 留言板位置 */
#twikoo {
  margin: 30px 0px;
}

/* 留言板位置 */
#twikoo .tk-comments-container a {
  text-decoration: none;
  color: #3e98f2;
}

</style>