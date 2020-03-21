# vuepress-plugin-go-top

<p align="center">
   <a href="https://www.npmjs.com/package/vuepress-plugin-go-top" target="_blank"><img alt="npm" src="https://img.shields.io/npm/v/vuepress-plugin-go-top.svg"></a>
   <a href="https://github.com/SigureMo/vuepress-plugin-go-top/stargazers" target="_blank"><img alt="GitHub stars" src="https://img.shields.io/github/stars/SigureMo/vuepress-plugin-go-top"></a>
   <a href="https://www.npmjs.com/package/vuepress-plugin-go-top" target="_blank"><img alt="downloads" src="https://img.shields.io/npm/dt/vuepress-plugin-go-top.svg"></a>
   <a href="https://www.npmjs.com/package/vuepress-plugin-go-top" target="_blank"><img alt="downloads" src="https://img.shields.io/npm/dm/vuepress-plugin-go-top.svg"></a>
   <a href="https://github.com/SigureMo/vuepress-plugin-go-top/blob/master/LICENSE" target="_blank"><img alt="GitHub license" src="https://img.shields.io/github/license/SigureMo/vuepress-plugin-go-top"></a>
</p>

- Website: [www.sigure.xyz/vuepress-lovely-plugins/](https://www.sigure.xyz/vuepress-lovely-plugins/)
- MyBlog: [www.sigure.xyz](https://www.sigure.xyz/)

## Install

``` bash
yarn add vuepress-plugin-go-top -D
# or use npm
npm i vuepress-plugin-go-top -D
```

## Usage

``` javascript
// .vuepress/config.js
module.exports = {
  plugins: ['go-top']
}
```

## Responsive breakpoints

``` stylus
// .vuepress/styles/palette.styl

$MQWide ?= 1440px
$MQMobile ?= 768px
```

## Thanks

- [GoTop](https://github.com/MisakaTAT/GoTop)
- [@vuepress/plugin-back-to-top](https://github.com/vuejs/vuepress/blob/master/packages/%40vuepress/plugin-back-to-top/BackToTop.vue)