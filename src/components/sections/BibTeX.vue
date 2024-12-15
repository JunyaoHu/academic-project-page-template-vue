<script>
export default {
  data() {
    return {
      bibtex: [
        "@article{junyaohu2023template,",
        "    title={Academic Project Page Template Vue},",
        "    author={Hu, Junyao},",
        "    journal={GitHub},",
        "    year={2023}",
        "}",
      ],
    }
  },
  methods: {
    copyVal() {
      let oInput = document.createElement('textarea');
      let text = document.getElementsByTagName('pre')[0].innerText;
      // console.log(text);
      oInput.value = text;
      document.body.appendChild(oInput);
      oInput.select();
      document.execCommand('Copy');
      this.$message.success('Copy Successfully');
      oInput.remove();
    }
  }
}

</script>

<template>
  <div>
    <el-divider />
      
      <el-row justify="center">
        <h1 class="section-title">BibTeX</h1>
      </el-row>
      
      <el-row justify="center">
        <el-col class='bibtex' :xs="24" :sm="20" :md="14" :lg="12" :xl="12">
          <el-scrollbar style="margin: 10px 20px 5px 20px;" @click="copyVal()" >
            <div style="text-align: center; color: var(--el-text-color-secondary);">🖱️ Click here to copy BibTex.</div> 
            <pre><code v-for="b in bibtex" class="code">{{ b }}<br/></code></pre>
          </el-scrollbar>
        </el-col>
      </el-row>

  </div>
</template>

<style scoped>

.scrollbar-flex-content {
  display: flex;
}

/* 代码属性 */
.code {
  font-family: Consolas, monospace;
}

/* 卡片属性 */
.bibtex {
  margin: 20px 0px;
  padding-top: 5px;
  box-shadow: var(--el-box-shadow-light); 
  border-radius: 10px;
}

/* 卡片悬浮 */
.bibtex:hover {
  box-shadow: var(--el-box-shadow); 
}

/* 卡片点击 */
.bibtex:active{
  box-shadow: var(--el-box-shadow-lighter); 
}
</style>