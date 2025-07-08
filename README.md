# academic-project-page-template-vue

![img](https://github.com/user-attachments/assets/0b6084a8-ad9c-4a1b-81b2-1f9591c7eabb)

> This project is in development, and welcome any suggestions.

This Vue-based repository is developed for an academic paper page template. It enables researchers to promote papers conveniently and intuitively. 

Now it support:
  - Icons of paper logo, author and affiliation
  - Markdown (using `.MDX` file)
  - Carousel
  - Video (local, bilibili iframe, youtube iframe)
  - ECharts
  - Math LaTex Formula
  - 3D and 3DGS model
  - Other components used to visualize model results
  - One-click copying of BibTeX
  - Comment area
  - ...

**Usage Example**

- https://junyaohu.github.io/academic-project-page-template-vue/
- https://longxuanx.github.io/CDFormer/
- https://ydove0324.github.io/Imaginarium/
- https://shailab-ipec.github.io/openfly/
- https://lstriving.github.io/SG-Mamba/
- https://cblxg.github.io/
- https://dajiebi.github.io/3D-Planner.github.io/
- https://freaky1122.github.io/weightless/
- https://jimm0011.github.io/PTTA-proj/
- https://shoutaosun.github.io/SAFE_display/
- https://ivyyy77.github.io/test2/
- https://shizw695.github.io/L2RSI/
- https://lakoj.github.io/denoising/
- https://sepermetric.github.io/
- https://auraluxmuse.github.io/
- https://yyyyyxie.github.io/textflux-site/
- https://bolixinyu.github.io/CCA-Attention-Page/
- https://wanghaowen19.github.io/AeroBrain/
- https://eavianwoo.github.io/singsPage/
- https://bolixinyu.github.io/FDVS/
- https://jimm0011.github.io/MEKD-proj/
- https://emotion-director.github.io/
- https://koorye.github.io/proj/Inspire/
- https://koorye.github.io/proj/PCD/
- More ...

**Deployment Tutotial Video**: https://www.bilibili.com/video/BV1oUrfYzEqZ

## Installation

**1. Github: Create a new repository**

Click `Create a new repository` to create a new copied repository based on this template for your site

![image](https://github.com/user-attachments/assets/e828d5bf-1269-4602-b2ca-c7d20b9c7fe1)

- if your repo name is `yourname.github.io`, your site will be on `yourname.github.io`
- if your repo name is `xxx`, your site will be on `yourname.github.io/xxx`

![image](https://github.com/user-attachments/assets/38e7f97f-2fc9-446e-bdf2-53f1691b9f71)

Reference: https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site#creating-a-repository-for-your-site

**2. Github: Edit vite config**

in file `vite.config.js`, you should edit the `base` to your repo name xxx

- if your repo name is `yourname.github.io`, set `base:'/',`
- if your repo name is `xxx`, set `base:'/xxx',`

```
base:'/xxx',
```

> This step is just so that you can intuitively understand that the website can work normally in your repository, and you can also make modifications manually in the following steps. 

**3. Github: Publish**

Choose `gh-pages` branch to show your website on github, then you will see your website on `xxx.github.io` or `yourname.github.io/xxx`

![image](https://github.com/user-attachments/assets/c0d7198f-6254-48e7-bc23-924ce065eb53)

Reference: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-from-a-branch

**4. Local PC: Prepare Vue environment**
 - install nodejs: (https://nodejs.org/zh-cn)
 - install vue: `npm create vue@latest` (https://cn.vuejs.org/guide/quick-start.html)
  
**5. Local PC: `Git clone` your new repo xxx**

**6. Local PC: install dependencies**

`npm i` to install necessary vue dependencies 

**7. Local PC: Edit and preview your website**

`npm run dev` to preview your website on your local pc, edit by yourself until you feel nice

**8. Local PC: `git push`**

`git push` to your copied repo, then .github/workflows will do the Github action to generate `gh-pages` branch automatically, you can wait a minute, `xxx.github.io` or `yourname.github.io/xxx` will be updated automatically.

**9. After the first deployment**

If you want to update your website again, you can edit your website locally and git push to your repo, `gh-pages` branch and the website will be both updated automatically soon.

## How to edit this template?

- Edit the content `<scripts>` in `.vue`, I have wrote some useful comments.

For example, you can change the original content to your own info (like paper's tile, logo, your name, your address, and the guidance buttons of your other materials) in `src/components/sections/Title.vue`

```
const logo = ''
const title = ''
const title_color = ''
const title_supp = ''
const title_supp_color = ''
const btn_color = ''
const authors = [
  {
    name: "",
    icon: "",
    homepage: "",
    address_flag: ""
  },
  ...
]

const addresses = [
  {
    address_flag: "",
    name: "",
    icon: "",
    homepage: ""
  },
  ...
]

const news = ""

const emphases = [
  "",
  ...
]

const buttons = [
  {
    disabled: ,
    name: "",
    component: ,
  },
   ...
]
```

- If you want to change the layout and use other components, you can read Element Plus Doc (https://element-plus.org/zh-CN/component/overview.html).

## How to deploy your own comment area?

> Twikoo is divided into two parts: cloud functions and front-end. To integrate Twikoo on your website, you need to deploy both cloud functions and front-end at the same time. Please pay attention to keeping the two versions consistent when deploying.

There we have deploy the front-end for you, you should only build your own cloud functions.

See [here](https://twikoo.js.org/backend.html) for more details. We recomment that you use [vercel](https://twikoo.js.org/backend.html#vercel-%E9%83%A8%E7%BD%B2) to do this. This can be more arbitrary, depending on you.

After building your own cloud functions, you can edit the config in `src/components/sections/Comment.vue`:

```
// Fill in envId for Tencent Cloud environment; fill in address for Vercel environment (https://xxx.versel.app)
envId: 'https://<YOUR WEBSITE LINK>.vercel.app', 
// default: 'ap-shanghai'，Tencent Cloud: 'ap-shanghai' / 'ap-guangzhou'; Vercel: ''
region: '', 
// comment area language， more supported languages: https://github.com/twikoojs/twikoo/blob/main/src/client/utils/i18n/index.js
lang: 'zh-CN',
```

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=JunyaoHu/academic-project-page-template-vue&type=Date)](https://star-history.com/#JunyaoHu/academic-project-page-template-vue&Date)

## Acknowledgments
Parts of this project page were adopted from the [Nerfies](https://nerfies.github.io/) page.

## Website License
<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.
