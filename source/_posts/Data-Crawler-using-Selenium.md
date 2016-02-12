title: Data Crawler using Selenium
tags: ['資料前處理', '資料庫', 'Python']
toc: true
date: 2015-10-28 03:08:43
categories: 'Data Science'
description:
blog: 'blog'
---

## Data Crawler

在資料探勘中有一個概念是：`Data Driven`，意即從資料的角度出發，觀察存在這些資料中問題或規則。因此我們常常說資料是新一代工業革命中的寶藏，一個好的探勘，來自於一份具有潛力的資料，而這也是目前很多人遇到的問題：資料怎麼來，資料從哪裡來？

這次使用 Selenium 實作 Data Crawler，Selenium 主要是拿來模擬瀏覽器行為的工具，而我們也利用的功能，模擬使用者瀏覽資料的過程取得資料，進一步利用 beautifulsoup 將原始資料進行爬梳。

## Example

```python
from selenium import webdriver
from selenium.webdriver.support.ui import Select

# 開啟網頁
browser.get("http://taqm.epa.gov.tw/taqm/tw/MonthlyAverage.aspx")

# 模擬行為
selectSite = Select(browser.find_element_by_id("ctl15_ddlSite"))
selectSite.select_by_value(cite)
selectYear = Select(browser.find_element_by_id("ctl15_ddlYear"))
selectYear.select_by_value(str(year))
browser.find_element_by_id('ctl15_btnQuery').click()

# 取得資料
html_source = browser.page_source

# 關閉瀏覽器
browser.quit();
```

```python 
from bs4 import BeautifulSoup

# 取得資料進行整理
soup = BeautifulSoup(html_source, 'html.parser')
city = soup.find(id="ctl15_ddlSite").find_all('option', selected=True)[0].
```

	
## Repository

## Reference
[1] [Selenium - Web Browser Automation](www.seleniumhq.org/)
[2] [selenium-crawler](https://github.com/corywalker/selenium-crawler)
[2] [斧頭幫大挑戰](http://axe.g0v.tw/)

---
## License

<img src="http://i.creativecommons.org/l/by-sa/3.0/88x31.png" style="    margin: 0;">
本著作由[Chang Wei-Yaun (v123582)](https://www.facebook.com/v123582)製作，
以[創用CC 姓名標示-相同方式分享 3.0 Unported](http://creativecommons.org/licenses/by-sa/3.0/deed.zh_TW)授權條款釋出。