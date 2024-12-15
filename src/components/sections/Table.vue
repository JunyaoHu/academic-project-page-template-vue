<script lang="ts" setup>

// 表格数据
const tableData = [
{
    model: 'Model A',
    params: '10 B',
    value_a: '123',
    value_b: '321',
},
{
    model: 'Model B',
    params: '30 B',
    value_a: '456',
    value_b: '654',
},
{
    model: 'Model C',
    params: '20 B',
    value_a: '789',
    value_b: '987',
},
{
    model: 'Model D',
    params: '5 B',
    value_a: '100',
    value_b: '200',
},
]
</script>

<template>
    <div>
        <el-divider />

        <el-row justify="center">
            <h1 class="section-title">More Results</h1>
        </el-row>
        
        <!-- 数据表格 -->
        <el-row justify="center">
            <el-col :xs="24" :sm="20" :md="16" :lg="12" :xl="12">

                <!-- 卡片 -->
                <el-card class="card">

                    <!-- 默认tab -->
                    <el-tabs class="demo-tabs" model-value="Method A">

                    <!-- 第一个tab -->
                    <el-tab-pane label="Method A" name="Method A">

                        <!-- 表格数据 -->
                        <el-table 
                            :data="tableData"
                            :default-sort="{ prop: 'value_b', order: 'descending' }"
                            scrollbar-always-on
                        >
                            <el-table-column prop="model" label="Model" width="100" sortable/>
                            <el-table-column prop="params" label="#Params" min-width="120" sortable/>
                            <el-table-column prop="value_a" label="Value A" min-width="120" sortable/>
                            <el-table-column prop="value_b" label="Value B" min-width="120" sortable/>
                        </el-table>
                    </el-tab-pane>

                    <el-tab-pane label="Method B" name="Method B">
                        Method B
                    </el-tab-pane>

                    <el-tab-pane label="Method C" name="Method C">
                        Method C
                    </el-tab-pane>

                    <el-tab-pane label="Method D" name="Method D">
                        Method D
                    </el-tab-pane>
                    </el-tabs>

                </el-card>
            </el-col>
        </el-row>

    </div>
</template>

<style scoped>
.card {
    margin-top: 20px;
}
</style>
  