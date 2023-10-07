<script>
export default {
  data() {
    return {
        home: {
            name: "Home",
            link: "https://junyaohu.github.io/",
            svg: '<svg xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 576 512"><!--! Font Awesome Free 6.4.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path d="M543.8 287.6c17 0 32-14 32-32.1c1-9-3-17-11-24L512 185V64c0-17.7-14.3-32-32-32H448c-17.7 0-32 14.3-32 32v36.7L309.5 7c-6-5-14-7-21-7s-15 1-22 8L10 231.5c-7 7-10 15-10 24c0 18 14 32.1 32 32.1h32v69.7c-.1 .9-.1 1.8-.1 2.8V472c0 22.1 17.9 40 40 40h16c1.2 0 2.4-.1 3.6-.2c1.5 .1 3 .2 4.5 .2H160h24c22.1 0 40-17.9 40-40V448 384c0-17.7 14.3-32 32-32h64c17.7 0 32 14.3 32 32v64 24c0 22.1 17.9 40 40 40h24 32.5c1.4 0 2.8 0 4.2-.1c1.1 .1 2.2 .1 3.3 .1h16c22.1 0 40-17.9 40-40V455.8c.3-2.6 .5-5.3 .5-8.1l-.7-160.2h32z"/></svg>'
        },
        logo: {
            name: "OPT",
            link: "#",
            svg: '<svg xmlns="http://www.w3.org/2000/svg" height="1.15em" viewBox="0 0 512 512"><!--! Font Awesome Free 6.4.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path d="M256 512A256 256 0 1 0 256 0a256 256 0 1 0 0 512zM369 209L241 337c-9.4 9.4-24.6 9.4-33.9 0l-64-64c-9.4-9.4-9.4-24.6 0-33.9s24.6-9.4 33.9 0l47 47L335 175c9.4-9.4 24.6-9.4 33.9 0s9.4 24.6 0 33.9z"/></svg>'
        },
    }
  }
}
</script>

<template>
    <el-affix :offset="0">
    <el-menu 
        default-active="1"
        class="el-menu-demo"
        mode="horizontal"
        :ellipsis="false"
    >
        <el-menu-item index="0">
            <span class="btn_icon" v-html="home.svg"></span>
            <a :href=home.link>{{ home.name }} </a>
        </el-menu-item>
        <el-menu-item index="1">
            <span class="btn_icon" v-html="logo.svg"></span>
            <a :href=logo.link>{{ logo.name }} </a>
        </el-menu-item>
        <div class="flex-grow" />
            <el-sub-menu index="2">
            <template #title>More</template>
            <el-menu-item index="2-1"><a href="https://zzcheng.top/MPOT/">MPOT - ICCV 2023</a></el-menu-item>
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
    </el-affix>
</template>
  
<style scoped>

.flex-grow {
    flex-grow: 1;
}

li {
    font-size: 18px;
}

a {
    text-decoration: None;
    color: inherit;
}

</style>

<style>
.el-sub-menu__title {
    font-size: 18px;
}

.el-affix--fixed {
    box-shadow: 1px 2px 3px rgba(0, 0, 0, 0.2);
}

.el-affix--fixed>.el-menu {
    background-color: rgb(250,250,250,0.9);
}

.btn_icon {
    color: black;
}

.el-menu-item:hover {
    fill: #409EFF;
}

.el-menu-item.is-active {
    fill: #409EFF;
}

.el-menu--popup {
    min-width: 100%;
}

.el-menu--popup a {
    text-overflow: ellipsis;
    overflow: hidden;
}
</style>

<style scoped>
.el-popper {
    min-width: min(50%, 300px);
}
</style>

  