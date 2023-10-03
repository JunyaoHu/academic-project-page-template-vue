<script>
export default {
  data() {
    return {
        home: {
            name: "Home",
            link: "https://junyaohu.github.io/",
        },
        logo: {
            name: "Our Project Template is All You Need",
            link: "#",
        },
    }
  }
}
</script>

<template>
    <el-menu 
        default-active="1"
        class="el-menu-demo"
        mode="horizontal"
        :ellipsis="false"
    >
        <el-menu-item index="0">
            <a :href=home.link>{{ home.name }} </a>
        </el-menu-item>
        <el-menu-item index="1">
            <a :href=logo.link>{{ logo.name }} </a>
        </el-menu-item>
        <div class="flex-grow" />
            <el-sub-menu index="2">
            <template #title>More Research</template>
            <el-menu-item index="2-1"><a href="https://zzcheng.top/MPOT/" target="_blank">Multiple Planar Object Tracking - ICCV 2023</a></el-menu-item>
            <el-menu-item index="2-2">item two</el-menu-item>
            <el-menu-item index="2-3">item three</el-menu-item>
                <el-sub-menu index="2-4">
                <template #title>item four</template>
                <el-menu-item index="2-4-1">item one</el-menu-item>
                <el-menu-item index="2-4-2">item two</el-menu-item>
                <el-menu-item index="2-4-3">item three</el-menu-item>
                </el-sub-menu>
            </el-sub-menu>
    </el-menu>
</template>
  
<style scoped>
.flex-grow {
    flex-grow: 1;
}

a {
    text-decoration: None;
    color: inherit;
}

</style>

  