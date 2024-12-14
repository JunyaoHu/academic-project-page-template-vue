<script>

// 评论配置
// Twikoo 支持腾讯云、Vercel、Railway 等多种平台部署
// Based on Tencent CloudBase
// See: https://twikoo.js.org

import { onMounted, onUnmounted } from 'vue';

// .el-button {
//   display: inline-block;
//     line-height: 1;
//     white-space: nowrap;
//     cursor: pointer;
//     background: #FFF;
//     border: 1px solid #DCDFE6;
//     color: #606266;
//     -webkit-appearance: none;
//     text-align: center;
//     -webkit-box-sizing: border-box;
//     box-sizing: border-box;
//     outline: 0;
//     margin: 0;
//     -webkit-transition: .1s;
//     transition: .1s;
//     font-weight: 500;
//     -moz-user-select: none;
//     -webkit-user-select: none;
//     -ms-user-select: none;
//     padding: 12px 20px;
//     font-size: 14px;
//     border-radius: 4px;
// }
export default {
  // 这个钩子函数会在组件挂载到 DOM 之后被自动调用，
  // 非常适合用来初始化 Twikoo 评论插件。
  // 在mounted函数内部，通过调用twikoo.init方法，
  // 并传入相应的配置参数（如envId和el等，根据实际情况填写和配置可选参数）
  // 来完成 Twikoo 的初始化工作，使其能够正确地在页面上展示评论框
  // 并与后端环境交互（前提是后端环境已正确配置好对应的envId等相关设置）。
  setup() {
    onMounted(() => {

      const cdnScript = document.createElement('script');
      // 一个修改过后的的 twikoo js 版本，不然直接导入sdn的话和element原版内容的冲突
      cdnScript.src = '/src/assets/twikoo/twikoo.junyaohu.js';
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
      <el-col :span="18">
        <div id="twikoo"></div>
      </el-col>
    </el-row>
  </div>
</template>

<style>

/* 不建议各位改这里，这里有点乱 */

/* 留言板位置 */
#twikoo {
  margin: 30px 0px;
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

#twikoo pre {
  border: 0.5px solid #bcbcbc;
  border-radius: 5px;
  padding: 10px;
  background: #ebeeff;
}

#twikoo code {
  font-family: 'Consolas';
  font-size: 14px;
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

.tk-content {
  background: #eeffee;
  border-radius: 5px;
  box-shadow: 0px 0px 3px #dadada;
  padding: 20px 20px;
}

.tk-replies .tk-content {
  background: #f6faf6;
  border-radius: 5px;
  box-shadow: 0px 0px 3px #dadada;
  padding: 20px 20px;
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