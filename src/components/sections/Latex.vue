<script lang="ts">
import { defineComponent } from 'vue'
import { VueLatex } from 'vatex'

export default defineComponent({
  components: {
    VueLatex
  }
})
</script>

<template>
  <div>
    <el-divider />

    <el-row justify="center">
      <h1 class="section-title">Latex</h1>
    </el-row>

    <el-row justify="center">
      <el-col :xs="24" :sm="20" :md="16" :lg="12" :xl="12">
        <p>
        Thanks to
        <a href="https://katex.org/docs/options.html" target="_blank">KaTex</a>
        and
        <a href="https://github.com/Shimada666/VaTex" target="_blank">VaTex</a>,
        now we can show an inline
        <VueLatex expression="\LaTeX" />
        formula, like
        <VueLatex expression="1+1=2" />.
        And we can show an interline formula like this: 
        <VueLatex expression="
            D(x) = \begin{cases}
            \lim\limits_{x \to 0} \frac{a^x}{b+c}, & x<3 \\
            \pi, & x=3 \\
            \int_a^{3b}x_{ij}+e^2 \mathrm{d}x,& x>3 \\
            \end{cases}
          " display-mode />
        </p>
      </el-col>
    </el-row>
  </div>
</template>

<style scoped>

</style>