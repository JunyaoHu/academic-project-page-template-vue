<template>
  <div>

    <el-divider />

    <!-- 标题 -->
    <el-row justify="center">
        <h1 class="section-title">Detail Discussion</h1>
    </el-row>

    <el-row justify="center">
        <el-col :xs="24" :sm="20" :md="16" :lg="12" :xl="12">

            <!-- 折叠列表 -->
            <el-collapse model-value="1" class="collapse" accordion >

                <!-- 第一个折叠列表信息 -->
                <el-collapse-item title="Consistency" name="1">
                    <div>
                        Consistent with real life: in line with the process and logic of real
                        life, and comply with languages and habits that the users are used to;
                    </div>
                </el-collapse-item>

                <el-collapse-item title="Feedback" name="2">
                    <div>
                        Operation feedback: enable the users to clearly perceive their
                        operations by style updates and interactive effects;
                    </div>
                </el-collapse-item>

                <el-collapse-item title="Efficiency" name="3">
                    <div>
                        Simplify the process: keep operating process simple and intuitive;
                    </div>
                </el-collapse-item>

                <el-collapse-item title="Controllability" name="4">
                    <div>
                        Decision making: giving advices about operations is acceptable, but do
                        not make decisions for the users;
                    </div>
                </el-collapse-item>
            </el-collapse>
        </el-col>
    </el-row>

  </div>
</template>
  
<script>
</script>

<style scoped>
.collapse {
    margin-top: 20px;
}
</style>
