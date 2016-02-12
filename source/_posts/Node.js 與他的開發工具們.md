title: Node.js 與他的開發工具們
tags:
  - 環境設定
  - Node
toc: true
blog: blog
date: 2016-02-06 00:40:20
categories: 'Web development'
description:
---

## Introduction

近年來隨著 Node.js 的發展及 Open Source 社群的貢獻，有越來越多好用且方便的開發工具，善加使用這些工具可加速整體開發進度。

* 版本管理工具
  * nvm
* 套件管理工具
  * npm
  * bower
* 自動化流程工具
  * grunt
  * gulp
* 打包工具
  * webpack
  * browserify
* 轉換工具
  * babel

## Node 版本管理工具

### nvm

由於開發過程很有可能不同 node 版本的需求，因此使用 nvm (Node Version Manager ) 這個工具。可以在電腦上安裝及快速切換到不同版本的 node。

## 套件管理工具

套件管理工具可以依據套件的相依性來安裝，簡單來說，開發者不用再去煩惱套件相依性問題。多人開發的情況下也能同步不同開發者之間的版本問題。

### npm

npm (Node Package Manager) 是 Node.js 下的主流套件管理程式，用來管理或安裝後端開發所需要的 Package。

### bower

bower 是 Twitter 團隊開發的一套網頁工具，用來管理或安裝前端開發所需要的 Package。

## 自動化流程工具

自動化流程工具作為構建工具，將專案封裝為可最終輸出的格式，通常包含大量自動化流程。
常用來執行 JS/CSS 打包壓縮、SASS/LESS/CoffeeScript 編譯、單元測試等工作，常被拿來當成開發自動化的引擎。 
常見的有 grunt ， gulp ，現在流行用 npm scripts 直接取代。

## 打包工具

處理 module 相依關係，將多支 javascript 檔案合成一支並在過程中做轉換處理。像是 webpack 及 browserify。

## 轉換工具

### babel
babel 是一個Javascript程式碼的編譯器，主要是因為目前大部份的瀏覽器，它們可以支援的Javascript版本，還沒達到最新版本ES2015(或稱ES6)的標準，要透過編譯器先進行與瀏覽器相容的編譯。

## Reference

[1] [coodoo/webpack-guide](https://github.com/coodoo/webpack-guide)
[3] [Gulp, Grunt, Bower以及npm](http://blog.darkthread.net/post-2014-09-25-gulp-grunt-bower-npm.aspx)
[2] [现代 Javascript 工具漫游指南](http://www.reqianduan.com/3005.html)
[4] [《嗨猫》笔记：搭建开发环境](http://ihardcoder.github.io/node/js/sails/react/%E5%BB%BA%E7%AB%99%E7%AC%94%E8%AE%B0/2015/12/06/%E3%80%8A%E5%97%A8%E7%8C%AB%E3%80%8B%E7%AC%94%E8%AE%B0%EF%BC%9A%E6%90%AD%E5%BB%BA%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83.html)
[5] [6to5 JavaScript Transpiler 重新命名為 Babel](https://blog.wu-boy.com/2015/02/the-6to5-javascript-transpiler-has-renamed-to-babel/)
[6] [Javascript 設定開發React的環境](http://eddychang.me/javascript/233-setup-react-develop-env.html)


---
## License

<img src="http://i.creativecommons.org/l/by-sa/3.0/88x31.png" style="    margin: 0;">
本著作由[Chang Wei-Yaun (v123582)](https://www.facebook.com/v123582)製作，
以[創用CC 姓名標示-相同方式分享 3.0 Unported](http://creativecommons.org/licenses/by-sa/3.0/deed.zh_TW)授權條款釋出。
