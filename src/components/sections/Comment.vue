<script>
twikoo.init({
  envId: 'https://blog-comment-h866w5ycd-junyaohu.vercel.app/', // 腾讯云环境填 envId；Vercel 环境填地址（https://xxx.vercel.app）
  el: '#tcomment', // 容器元素
  region: 'ap-shanghai', // 环境地域，默认为 ap-shanghai，腾讯云环境填 ap-shanghai 或 ap-guangzhou；Vercel 环境不填
  path: window.location.pathname, // 用于区分不同文章的自定义 js 路径，如果您的文章路径不是 location.pathname，需传此参数
  lang: 'zh-CN', // 用于手动设定评论区语言，支持的语言列表 https://github.com/twikoojs/twikoo/blob/main/src/client/utils/i18n/index.js
})
</script>

<template>
  <div>
    <el-row>
      <h1 class="title1">Comment</h1>
    </el-row>
    <el-row>
      <el-col class='bibtex' :span="20">
        <div id="tcomment"></div>
      </el-col>
    </el-row>
  </div>
</template>