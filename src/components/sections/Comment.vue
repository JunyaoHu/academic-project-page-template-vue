<script>

// 评论配置
// Twikoo 支持腾讯云、Vercel、Railway 等多种平台部署
// Based on Tencent CloudBase
// See: https://twikoo.js.org

import { onMounted } from 'vue';

export default {
  setup() {
    onMounted(() => {

      const cdnScript = document.createElement('script');
      // 一个修改过后的的 twikoo js 版本，不然直接导入cdn的话和element原版内容的冲突
      cdnScript.src = './twikoo/twikoo.junyaohu.js';
      // cdnScript.src = 'https://cdn.staticfile.org/twikoo/1.6.40/twikoo.all.min.js';
      cdnScript.async = true;
    
      const loadSecondScript = () => { twikoo.init({
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
      }

      cdnScript.addEventListener('load', loadSecondScript);
      document.body.appendChild(cdnScript);

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
      <el-col :xs="24" :sm="24" :md="24" :lg="16" :xl="12" >
        <div id="twikoo"></div>
      </el-col>
    </el-row>
  </div>
</template>

<style>

/* 不建议各位改这里，这里有点乱 */

/* 留言板位置 */
#twikoo {
  margin: 30px 0px 0px 0px;
}

#twikoo .tk-owo-emotion {
  width: 1.5em;
}

#twikoo img {
  height: 100%;
  width: 100%;
}

#twikoo .el-input-group__prepend {
  border: none;
}

#twikoo .el-textarea__inner {
  border: none;
}

#twikoo .el-button--small {
  height: 100%;
}

/* 留言板头像属性 */
.tk-avatar {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  margin-right: 10px
}

.tk-avatar {
  box-shadow: 0px 0px 3px #dadada;;
}

/* 留言板链接属性 */
.tk-actions a {
  text-decoration: none;
  color: #3e98f2;
}

.tk-extras {
  margin: 5px 0px 20px 0px;
}

/* 留言板回复链接属性 */
.tk-ruser {
  text-decoration: none;
  color: #3e98f2;
}

/* twikoo链接属性 */
.tk-footer a {
  text-decoration: none;
  color: #3e98f2;
}

</style>
