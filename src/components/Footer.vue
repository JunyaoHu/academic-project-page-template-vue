<script>

export default {
  data() {
    return {
      text:" The template is borrowed from Nerfies"
    }
  }
}
</script>

<template>
  <div class="bg">
    <el-row>
      <el-col :xs="20" :sm="20" :md="16" :lg="12" :xl="12">
          <p class="footer">
            The template is inspired by <a class="footer_link" href="https://github.com/nerfies/nerfies.github.io">Nerfies</a>, powered by <a class="footer_link" href="https://vuejs.org/">Vue</a>.<br/>
            You can fork🛠️ / star✨/ PR📃 this template<br/>
            from <a class="footer_link" href="https://github.com/JunyaoHu/academic-project-page-template-vue">Academic Project Page Template Vue</a>.
          </p>
      </el-col>
    </el-row>
  </div>
</template>

<style scoped>
.bg {
  background-color: rgb(235, 235, 235);
}

.footer {
  text-align: center;
}

a.footer_link {
  color: #3273dc;
  text-decoration: none;
}

a.footer_link:hover {
  color: #363636;
  border-bottom: dotted;
}

</style>