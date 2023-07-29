<script>
export default {
  data() {
    return {
      title: 'Our Project Template is All You Need',
      authors: [
        {
          name: "Junyao Hu",
          icon: "https://junyaohu.github.io/img/avatar.png",
          homepage: "https://junyaohu.github.io/",
          address_flag: "1"
        },
        {
          name: "Another author",
          icon: "https://junyaohu.github.io/img/avatar.png",
          homepage: "https://junyaohu.github.io/",
          address_flag: "2"
        },
        {
          name: "Your Tutor",
          icon: "https://junyaohu.github.io/img/avatar.png",
          homepage: "https://junyaohu.github.io/",
          address_flag: "1"
        },
      ],
      addresses: [
        {
          address_flag: "1",
          name: "Nankai University",
          icon: "",
          homepage: "https://cv.nankai.edu.cn/"
        },
        {
          address_flag: "2",
          name: "Another University",
          icon: "",
          homepage: "https://cv.nankai.edu.cn/"
        },
      ],
      emphasis: "Something that needs to be emphasized 🥰",
      buttons: [
        {
          disabled: false,
          name: "Paper",
          link: "https://junyaohu.github.io/",
          svg: '<svg xmlns="http://www.w3.org/2000/svg" height="1.5em" viewBox="0 0 512 512"><!--! Font Awesome Free 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><style>svg{fill:#ebebeb}</style><path d="M0 64C0 28.7 28.7 0 64 0H224V128c0 17.7 14.3 32 32 32H384V304H176c-35.3 0-64 28.7-64 64V512H64c-35.3 0-64-28.7-64-64V64zm384 64H256V0L384 128zM176 352h32c30.9 0 56 25.1 56 56s-25.1 56-56 56H192v32c0 8.8-7.2 16-16 16s-16-7.2-16-16V448 368c0-8.8 7.2-16 16-16zm32 80c13.3 0 24-10.7 24-24s-10.7-24-24-24H192v48h16zm96-80h32c26.5 0 48 21.5 48 48v64c0 26.5-21.5 48-48 48H304c-8.8 0-16-7.2-16-16V368c0-8.8 7.2-16 16-16zm32 128c8.8 0 16-7.2 16-16V400c0-8.8-7.2-16-16-16H320v96h16zm80-112c0-8.8 7.2-16 16-16h48c8.8 0 16 7.2 16 16s-7.2 16-16 16H448v32h32c8.8 0 16 7.2 16 16s-7.2 16-16 16H448v48c0 8.8-7.2 16-16 16s-16-7.2-16-16V432 368z"/></svg>'
        },
        {
          disabled: true,
          name: "Demo (soon)",
          link: "#",
          svg: '<svg xmlns="http://www.w3.org/2000/svg" height="1.5em" viewBox="0 0 512 512"><!--! Font Awesome Free 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><style>svg{fill:#ebebeb}</style><path d="M234.5 5.7c13.9-5 29.1-5 43.1 0l192 68.6C495 83.4 512 107.5 512 134.6V377.4c0 27-17 51.2-42.5 60.3l-192 68.6c-13.9 5-29.1 5-43.1 0l-192-68.6C17 428.6 0 404.5 0 377.4V134.6c0-27 17-51.2 42.5-60.3l192-68.6zM256 66L82.3 128 256 190l173.7-62L256 66zm32 368.6l160-57.1v-188L288 246.6v188z"/></svg>'
        },
        {
          disabled: true,
          name: "Video (soon)",
          link: "#",
          svg: '<svg xmlns="http://www.w3.org/2000/svg" height="1.5em" viewBox="0 0 512 512"><!--! Font Awesome Free 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><style>svg{fill:#ebebeb}</style><path d="M448 32H361.9l-1 1-127 127h92.1l1-1L453.8 32.3c-1.9-.2-3.8-.3-5.8-.3zm64 128V96c0-15.1-5.3-29.1-14-40l-104 104H512zM294.1 32H201.9l-1 1L73.9 160h92.1l1-1 127-127zM64 32C28.7 32 0 60.7 0 96v64H6.1l1-1 127-127H64zM512 192H0V416c0 35.3 28.7 64 64 64H448c35.3 0 64-28.7 64-64V192z"/></svg>'
        },
        {
          disabled: true,
          name: "Code (soon)",
          link: "#",
          svg: '<svg xmlns="http://www.w3.org/2000/svg" height="1.5em" viewBox="0 0 384 512"><!--! Font Awesome Free 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><style>svg{fill:#ebebeb}</style><path d="M64 0C28.7 0 0 28.7 0 64V448c0 35.3 28.7 64 64 64H320c35.3 0 64-28.7 64-64V160H256c-17.7 0-32-14.3-32-32V0H64zM256 0V128H384L256 0zM153 289l-31 31 31 31c9.4 9.4 9.4 24.6 0 33.9s-24.6 9.4-33.9 0L71 337c-9.4-9.4-9.4-24.6 0-33.9l48-48c9.4-9.4 24.6-9.4 33.9 0s9.4 24.6 0 33.9zM265 255l48 48c9.4 9.4 9.4 24.6 0 33.9l-48 48c-9.4 9.4-24.6 9.4-33.9 0s-9.4-24.6 0-33.9l31-31-31-31c-9.4-9.4-9.4-24.6 0-33.9s24.6-9.4 33.9 0z"/></svg>'
        },
      ],
    }
  }
}
</script>

<template>
  <div>
    <el-row class="title">
      <el-col :span="22"><h1>{{ title }}</h1></el-col>
    </el-row>

    <el-row>
      <span v-for="author in authors">
        <a :href=author.homepage>
          <el-button type="primary" text>
            <span class="author">
              {{ author.name }}<sup v-if="author.address_flag" style="color: #606266">{{ author.address_flag }}</sup>
            </span>
          </el-button>
        </a>
      </span>
    </el-row>

    <el-row>
      <span v-for="address in addresses">
        <a :href=address.homepage>
          <el-button type="" text>
            <span class="address">
              <sup v-if="address.address_flag" style="color: #606266">{{ address.address_flag }}</sup>{{ address.name }}
            </span>
          </el-button>
        </a>
      </span>
    </el-row>

    <el-row class="emphasis">
      {{ emphasis }}
    </el-row>

    <el-row justify="center">
      <span class="btn" v-for="button in buttons">
        <a :href=button.link class="btn_link">
          <el-button class="btn_font" size="large" color="#7e0c6d" :disabled="button.disabled">
            <span class="btn_icon" v-html="button.svg"></span>
            <span>{{ button.name }}</span>
          </el-button>
        </a>
      </span>
    </el-row>
  </div>
</template>

<style>

.el-row {
  justify-content: center;
  margin-bottom: 10px;
}

a {
  color: hsl(204, 86%, 53%);
  text-decoration: none;
}

.btn {
  margin: 4px 5px;
}

.emphasis {
  color: chocolate;
  font-weight: bold;
  margin: 15px;
  font-size: 22px;
  text-align: center;
}

.btn_icon {
  margin-right: 8px;
  display: flex;
}

.btn_font {
  font-size: 18px;
}

.title {
  font-family: "MyFont", Verdana, sans-serif;
  letter-spacing: 2px;
  font-size: 32px;
  margin-top: 30px;
  margin-bottom: 0px;
  text-align: center;
}

.author {
  font-size: 20px;
}

.address {
  font-size: 20px;
}

</style>