<script lang="ts" setup>

import { ElIcon } from 'element-plus'
import { Document, Files, MagicStick, Picture, DataAnalysis, Film } from '@element-plus/icons-vue'
import 'element-plus/es/components/icon/style/css'
import { disconnect } from 'echarts';

// 标题
const title = 'Academic Project Page Template'

// 标题颜色
const title_color = '#000000'

// 标题补充，没有则置为""即可
const title_supp = ' (Vue based)'

// 标题补充颜色
const title_supp_color = '#42B883'

// 按钮颜色
const btn_color = '#7e0c6d'

// 作者清单（包含作者姓名、头像、主页、地址序号）
const authors = [
  {
    name: "Your Name",
    icon: "https://junyaohu.github.io/img/avatar.png",
    homepage: "https://junyaohu.github.io/",
    address_flag: "1,#"
  },
  {
    name: "Anya Forger",
    icon: "http://img.92fa.com/pic/TX1439_01.jpg",
    homepage: "https://www.bilibili.com/video/BV1jv4y1P7Bb",
    address_flag: "2,#"
  },
  {
    name: "BugCat Capoo",
    icon: "https://img.moegirl.org.cn/common/0/01/%E7%8C%AB%E7%8C%AB%E8%99%AB%E5%92%96%E6%B3%A2.jpg",
    homepage: "https://zh.moegirl.org.cn/%E7%8C%AB%E7%8C%AB%E8%99%AB%E5%92%96%E6%B3%A2",
    address_flag: "1,*"
  },
]

// 地址清单（包含地址名称、头像、主页、地址序号）
const addresses = [
  {
    address_flag: "1",
    name: "Home University",
    icon: "https://avatars.githubusercontent.com/u/85953864?s=200&v=4",
    homepage: "https://github.com/hmuniversity"
  },
  {
    address_flag: "2",
    name: "IKUN University",
    icon: "https://gw.alicdn.com/imgextra/O1CN01S1PoyX1IZuTHAfhNs_!!6000000000908-2-yinhe.png",
    homepage: "https://www.bilibili.com/video/BV178411Y7QB"
  },
]

// 共一和通讯提示
const con_and_corresponding_author = 
  "# = Equal Contribution. * = Corresponding Author."


// 强调内容
const emphases = [
  "[ABCD 2024] Poster",
  "This template project is still under development.",
  "Welcome any suggestion. 🥰",
]

// 提供引导资料链接
const buttons = [
  {
    disabled: false,
    name: "Paper",
    link: "https://junyaohu.github.io/",
    component: Document,
  },
  {
    disabled: true,
    name: "中译版",
    component: Document,
  },
  {
    disabled: true,
    name: "Code",
    component: Files,
  },
  {
    disabled: true,
    name: "Demo",
    component: MagicStick,
  },
  {
    disabled: true,
    name: "Poster",
    component: Picture,
  },
  {
    disabled: true,
    name: "Slide",
    component: DataAnalysis,
  },
  {
    disabled: true,
    name: "Video",
    component: Film,
  },
]

</script>

<template>
  <div>

    <!-- 文章标题 -->
    <el-row justify="center">
      <el-col :span="20">
        <h1 class="paper-title">
          <span v-if="title" :style="{color:title_color}"> {{ title }}</span>
          <span v-if="title_supp" :style="{color:title_supp_color}"> {{ title_supp }}</span>
        </h1>
      </el-col>
    </el-row>

    <!-- 作者名单 -->
    <el-row justify="center">
      <a :href=author.homepage v-for="author in authors">
        <el-button class="title-button" type="primary" text>
          <el-avatar v-if="author.icon" :size="40" :src="author.icon" />
          <span class="author">
            {{ author.name }}<sup v-if="author.address_flag" class="name_sup">{{ author.address_flag }}</sup>
          </span>
        </el-button>
      </a>
    </el-row>

    <!-- 地址名单 -->
    <el-row justify="center">
      <a :href=address.homepage v-for="address in addresses">
        <el-button class="title-button" type="primary" text>
          <el-avatar v-if="address.icon" :size="40" :src="address.icon" />
          <span class="address">
            <sup v-if="address.address_flag" class="address_sup">{{ address.address_flag }}</sup>{{ address.name }}
          </span>
        </el-button>
      </a>
    </el-row>

    <!-- 共一和通讯提示内容 -->
    <el-row justify="center" class="con-cor">
        {{ con_and_corresponding_author }}
    </el-row>

    <!-- 强调内容 -->
    <el-row justify="center" class="emphasis" v-for="emphasis in emphases">
        {{ emphasis }}
    </el-row>

    <!-- 提供引导按钮 -->
    <el-row :span="10" justify="center">
      <a :href=button.link v-for="button in buttons">
        <el-button class="guidance-button" size="large" :color="btn_color" :disabled="button.disabled">
          <el-icon :size="22">
            <component :is="button.component" />
          </el-icon>
          <span class="btn-text">{{ button.name }}</span>
        </el-button>
      </a>
    </el-row>
  </div>
</template>

<style>

/* 文章标题字体、字间距、居中排布、字号 */
.paper-title {
  font-family: "MyFont", Verdana, sans-serif;
  letter-spacing: 2px;
  font-size: 42px;
  text-align: center;
}

.title-button {
  margin: 10px 3px;
}

.guidance-button {
  margin: 10px 6px;
}

.author {
  font-size: 18px;
  margin-left: 3px;
}

.name_sup {
  color: #606266; 
  margin-left: 3px;
}

.address {
  font-size: 14px;
}

.address_sup {
  color: #606266; 
  margin-right: 1px;
}

.el-avatar {
  margin-right: 6px;
  box-shadow: var(--el-box-shadow-lighter); 
}

.con-cor {
  font-family: Arial;
  font-size: 14px;
  margin: 18px 0px;
  text-align: center;
}

.emphasis {
  color: chocolate;
  font-weight: bold;
  margin: 8px;
  font-size: 22px;
  text-align: center;
}

.btn-text {
  font-size: 20px;
}

</style>