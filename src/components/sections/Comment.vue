<script>

// 评论配置
// Twikoo 支持腾讯云、Vercel、Railway 等多种平台部署
// Based on Tencent CloudBase
// See: https://twikoo.js.org

twikoo.init({
  // 腾讯云环境填 envId；Vercel 环境填地址（https://xxx.vercel.app）
  envId: 'https://blog-comment-nvoz-8o7dxhfbd-junyaohus-projects.vercel.app', 
  // 容器元素
  el: '#twikoo', 
  // 环境地域，默认为 ap-shanghai，腾讯云环境填 ap-shanghai 或 ap-guangzhou；Vercel 环境不填
  region: '', 
  // 用于区分不同文章的自定义 js 路径，如果您的文章路径不是 location.pathname，需传此参数
  // path: location.pathname,
  // 用于手动设定评论区语言，支持的语言列表 https://github.com/twikoojs/twikoo/blob/main/src/client/utils/i18n/index.js
  lang: 'zh-CN', 
})
</script>

<template>
  <div>
    <el-divider />
    
    <el-row justify="center">
      <h1 class="section-title">💬 Comment</h1>
    </el-row>
    
    <el-row justify="center">
      <el-col :span="22" >
        <div id="twikoo" ></div>
      </el-col>
    </el-row>
  </div>
</template>

<style scoped>

/* 摘要文字居中 */
p {
  text-align: justify;
}

#twikoo {
  margin-top: 100px;
}

input {
  border: solid #c1c1c1;
}

</style>