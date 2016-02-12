title: 用 Hexo 建立一個自己的部落格
tags: ['Hexo', 'Node']
toc: true
date: 2015-10-25 22:01:00
categories: 'Web development'
description:
blog: 'blog'
---

## 什麼是 hexo？

> [Hexo](https://hexo.io/zh-tw/) 是一個用 node 撰寫，支援 markdown 的 static blog template。

![Imgur](http://i.imgur.com/5fM26uC.png)

## 怎麼使用？

* 安裝及建立專案

要記得先安裝 node 及 npm ，再利用 npm 安裝 hexo，安裝之後會在目錄底下開了一個 hexo 專案。

```
$ npm install -g hexo-cli
# 利用 npm 安裝 hexo 在 global 
$ hexo init <folder>
# 建立一個 hexo 專案
$ cd <folder>
$ npm install
# 利用 npm 安裝相依套件
```

* 寫作

開一篇新文章的方法很簡單，使用內建指令，可以加 `layout` 參數決定版型。版型會存在 `./scaffolds` ，預設是 post 版型。隨後會在 `./source` 多了一個 markdown 檔案，這個就是建立的新文章。
 
```
$ hexo new [layout] <title> 
```

* 本機端發布

由於文章都是使用 markdown 格式存在，因此必須要轉成 html 才可以變成一個完整的網站，可以使用以下指令在產生。


```
$ hexo generate
```

* 發佈 & 部署

heox 有一個很方便的地方，可以使用 git 發布專案。可以參考 pulgin: hexo-deployer-git。設定在 `./_config.yml` 中的 deploy。

```
$ hexo server
# INFO  Hexo is running at 0.0.0.0:4000
$ hexo deploy
# INFO  Hexo is running at remote site
```

## 設定

hexo 的主要設定有兩個地方：

* `./_config.yml`: 全域的環境設定
* `./themes/<theme>/_config.yml`: 使用主題的環境設定

也有很多套件可以支援，可以上官方好好研究。

## 比較

static blog template 除了可以使用 Hexo 之外，各常用語言也都有類似的套件：

* Ruby  	: Jekyll
* Python  	: Hyde 
* PHP	  	: Phrozn
* JS 	 	: Hexo
 

## Reference

[1] [Hexo](https://hexo.io/zh-tw/)

---
## License

<img src="http://i.creativecommons.org/l/by-sa/3.0/88x31.png" style="    margin: 0;">
本著作由[Chang Wei-Yaun (v123582)](https://www.facebook.com/v123582)製作，
以[創用CC 姓名標示-相同方式分享 3.0 Unported](http://creativecommons.org/licenses/by-sa/3.0/deed.zh_TW)授權條款釋出。