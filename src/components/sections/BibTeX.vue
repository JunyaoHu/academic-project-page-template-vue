<script>
export default {
  data() {
    return {
      bibtex: [
        "@article{junyaohu2023template,",
        "    title={Our Project Template is All You Need},",
        "    author={Hu, Junyao},",
        "    journal={Something},",
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
    
    <el-row>
      <h1 class="title1">BibTeX</h1>
    </el-row>

    <el-row>
      <el-col class='bibtex' :xs="20" :sm="20" :md="14" :lg="12" :xl="12">
        <el-scrollbar style="margin: 10px 20px 5px 20px;" @click="copyVal()">
          <div style="text-align: center; color: var(--el-text-color-secondary);">Click here to copy BibTex.</div> 
          <pre><code v-for="b in bibtex" class="code">{{ b }}<br/></code></pre>
        </el-scrollbar>
      </el-col>
    </el-row>

  </div>
</template>

<style scoped>

.title1 {
  margin-bottom: 10px;
}

.scrollbar-flex-content {
  display: flex;
}

.code {
  font-family: Consolas, monospace;
}

.bibtex {
  box-shadow: var(--el-box-shadow-light); 
  border-radius: 10px;
}

.bibtex:hover {
  box-shadow: var(--el-box-shadow); 
}

.bibtex:active{
  box-shadow: var(--el-box-shadow-lighter); 
}
</style>