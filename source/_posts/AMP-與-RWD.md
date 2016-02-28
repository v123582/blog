title: AMP 與 RWD ?
tags:
  - Front-End
toc: true
blog: blog
date: 2016-02-29 01:07:09
categories: 'Web development'
description:
---

## 什麼是 AMP ？

> Instant. Everywhere. - [AMP](https://www.ampproject.org/)

行動網路的網頁讀取常常會有一些效能上的問題，因此 2015 年 10 月， Google 宣布 加速行動網頁（Accelerated Mobile Pages ， AMP）計畫。 AMP 是一個快速讀取行動網頁的框架，目的在於提高網頁內容的讀取速度，進而提升使用者體驗。在行動裝置下載網頁的時間，比過去快 4 倍，而且僅佔用原有 10分之一 的數據量。

AMP 有兩個主要目標：

* 為了提高人們試圖讀取行動設備上的內容體驗
* 為了更輕鬆地發佈內容

### 使用者體驗更快速

AMP page 會依賴 AMP javascript 引入內容到頁面上，AMP javascript 會讓內容的載入更加快速。此外所有的 AMP pages 和 AMP javascript 都是放在 Google 的 CDN 上。

### 發佈內容更輕鬆

由於 Facebook Instant Articles、Apple News 等即時新聞入口，已明顯對 Google 的核心廣告業務構成了威脅，Google 的 Instant Articles 可謂勢在必行，通過巨大流量與優化的呈現方式，來鞏固新聞類文章帶來的廣告業務優勢。 AMP 不同於 Facebook Instant Articles 和 Apple News 使用規定的資料格式，而是透過改善發佈策略來加速。這對於發佈者來說，是比較方便且簡單的作法。

## AMP vs RWD

AMP 和 RWD 都是因為行動網路裝置的興起，而衍伸出來的網頁發展技術。我們針對目的、作法、用途來釐清這兩者之間的差別。

### 目的

RWD 的目的是為了將傳統的網頁瀏覽，能隨著不同的使用者裝置，而有不同的顯示樣式。 AMP 則是重點在如何加速網路內容的存取。

### 做法

在現有的網站上如果想要達到 RWD 的效果，往往必須重新設計跟及一定幅度的修改網頁。但是 AMP 的話是在原本的網頁下，加入 AMP 的機制而不用重新規劃網頁的呈現。

### 用途

RWD 將可以用於一般的網頁，像是 web forms 和 custom applications。 AMP 將對於內容發佈的網站產生預期的效果，像是 news articles 和 blog entries。

### 小結

* AMP is not a replacement for RWD
* AMP does not validate device detection as a better technique than RWD

## SEO 與 UX

Google Search 定義了對於行動網路的排序主要依據兩點：(1) 使用者體驗 與 (2) 速度。 RWD 可以幫助實現手機上的使用者體驗，但通常會造成速度上的限制。但 AMP 可以同時滿足這兩點，因此 AMP 可以視為 SEO 上重點的工作。

## How to get start？

[Create Your First AMP Page](https://www.ampproject.org/docs/get_started/create_page.html)

## 結論

AMP 解決了一個很具體的問題：盡可能快速的發布內容。對於網站的發布內容快速將提供更好的使用者體驗。然而，AMP 對於 Web 表單和自定義 JavaScript 的網站還尚未完全支援。


## Reference

[1] [AMP vs Responsive Web Design](http://www.business2community.com/mobile-apps/amp-vs-responsive-web-design-01420003#l8J0tUXRTwfhZou3.97)
[2] [AMP and Responsive Web Design](http://responsivenews.co.uk/post/131144968568/amp-and-responsive-web-design)
[3] [How To Get Started With Accelerated Mobile Pages (AMP)](http://seo.ads-facebook.com.tw/?p=375)
[4] [[resolved] AMP vs RWD or AMP & RWD or simply AMP??](https://wordpress.org/support/topic/amp-vs-rwd-or-amp-rwd-or-simply-amp)
[5] [​Google拼速度　點閱新聞更快速](http://www.appledaily.com.tw/realtimenews/article/new/20160225/803026/)


---
## License

<img src="http://i.creativecommons.org/l/by-sa/3.0/88x31.png" style="    margin: 0;">
本著作由[Chang Wei-Yaun (v123582)](https://www.facebook.com/v123582)製作，
以[創用CC 姓名標示-相同方式分享 3.0 Unported](http://creativecommons.org/licenses/by-sa/3.0/deed.zh_TW)授權條款釋出。
