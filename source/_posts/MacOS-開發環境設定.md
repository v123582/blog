title: MacOS 開發環境設定
tags: ['環境設定']
toc: true
blog: blog
date: 2015-12-06 02:29:07
categories: 'System'
description:
---

## Package Manager
### Homebrew
Homebrew 是一套很好用的套件管理工具，有點像是 Ubuntu 上的 apt-get，可以幫助你快速安裝你所需要工具
### 安裝

```
$ ruby -e "$(curl -fsSL https://raw.github.com/mxcl/homebrew/go/install)"
```

### 使用

* `brew search` 搜尋套件
* `brew info` 查詢套件資訊
* `brew list` 已經裝了哪些套件
* `brew update` 更新 homebrew 
* `brew install` 安裝套件

### 其他

* [homebrew-cask](https://github.com/caskroom/homebrew-cask)：基於 Homebrew 的軟體安裝工具，可以快速透過 terminal 下載軟體

---

## Terminal
### itrem2 + Zsh(Z Shell) + Oh-My-Zsh
iTerm2 是社群開發出來取代 Mac OS X 內建的 Terminal(終端機) 的好用軟體，Zsh 是一個加強版的 Shell，多了一些人性化的功能，Oh-My-Zsh 則是一套好用的 Zsh 套件。

### 優點

* 與 bash 語法幾乎相容
* 錯字自動矯正
* 自動完成
* 歷史紀錄可以跨 Session 共享
* 內建 pager，不用每次都打 | less 分頁
* 更強大的檔名比對 (Filename Globbing)
* 更容易上手的 Script Language
* 有 Oh-My-Zsh 套件可以使用，Oh-My-Zsh 集合了很多好用的主題/套件
 
### 安裝

* [itrem2](http://iterm2.com/downloads.html)：直接從官網下載
* [Zsh](http://www.zsh.org/)：Mac 內建已經安裝
* [Oh-My-Zsh](https://github.com/robbyrussell/oh-my-zsh)

```
$ curl -L https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh | sh
```

### 主題/套件
安裝完之後，可以對主題/套件做一些調整，Oh-My-Zsh 本身就有非常多樣的[主題](https://github.com/robbyrussell/oh-my-zsh/wiki/themes)可以直接使用
主題/套件主要的設定在`~/.zshrc`

```
$ vim ~/.zshrc
```

內容設定如下：

```
ZSH_THEME = "agnoster"
# 將 ZSH_THEME 設為主題的名稱，以 agnoster 主題為例
plugins=( plugin1 plugin2 ... )
# plugins 是設定要使用的套件名稱，以空格分開。套件是要另外安裝的！
export LC_ALL=en_US.UTF-8
export LANG=en_US.UTF-8
# 中文設定的話要加上這兩行
```

> Note. agnoster 主題在中文字形方面可以會有問題，所以要改用 [Monaco for Powerline](https://github.com/supermarin/powerline-fonts/blob/master/Monaco/Monaco%20for%20Powerline.otf?raw=true) 字體，更改方式走介面即可
* iTerm -> Ｐreferences -> Profiles -> Text -> Change Font

另外，推薦幾個好用的套件
* [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)

### 完成圖
![shell.png](http://user-image.logdown.io/user/4431/blog/4465/post/230789/ONYsdKPwTgSFRlv8NAOV_shell.png)

<!---

## Editor
### **<font color='blue'>Sublime text 2</font>**
### 基本操作及常用快捷鍵
### 套件

---

## 系統變數設定

--->
---
## 其他
### [Git 版本控制的基本操作筆記](http://weiyuan.logdown.com/posts/230647)

---

## Reference
[1] [Homebrew](http://brew.sh/)
[2] [Oh-My-Zsh 讓你的終端機更強大更美觀](http://iphone4.tw/forums/showthread.php?t=206652)
[3] [简洁优雅的Mac OS X软件安装体验 - homebrew-cask](http://ksmx.me/homebrew-cask-cli-workflow-to-install-mac-applications/)


---
## License

<img src="http://i.creativecommons.org/l/by-sa/3.0/88x31.png" style="    margin: 0;">
本著作由[Chang Wei-Yaun (v123582)](https://www.facebook.com/v123582)製作，
以[創用CC 姓名標示-相同方式分享 3.0 Unported](http://creativecommons.org/licenses/by-sa/3.0/deed.zh_TW)授權條款釋出。