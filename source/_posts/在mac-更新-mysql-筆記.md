title: 在 MacOS 上安裝/更新 MySQL 筆記
tags: ['環境設定', 'MacOS', 'MySQL']
toc: true
date: 2016-01-26 16:29:07
categories: 'System'
description:
blog: 'blog'
---

## 在 Mac 上安裝 MySQL

1. 利用 brew 進行安裝，安裝後會預設一個不用輸入密碼的 root 帳號，安裝在 /usr/local/bin/mysql

	```
	$ brew install mysql
	```

2. 第一次使用，先更改密碼

	* 法一：手動更改

	```
	$ mysql -u root # 使用預設的 root 帳號連接 mysql
	mysql>
	mysql> USE mysql; # 切換到 mysql 資料表
	mysql> UPDATE user SET password=password('root') WHERE user='root'; # 設定 root 新的密碼
	mysql> exit 
	$ mysql -u root -p # 使用改過密碼的 root 帳號連接 mysql
	Enter password: **** # 輸入密碼才可以登入
	mysql>
	```

	* 法二：使用 mysql_secure_installation 修改

	mysql_secure_installation 提供了一些初始化 MySQL 的快速設定。除了要設定 root 設定密碼外，並加上一些安全權限的設定。

	```
	$ mysql_secure_installation
	> Enter current password for root (enter for none):
	# 輸入 root 的密碼，如果沒有設定過，直接按 Enter 鍵即可
	> Set root password? [Y/n] 
	# 設定 root 的密碼
	> Remove anonymous users? [Y/n] 
	# 移除 anonymous 使用者
	> Disallow root login remotely? [Y/n] # 取消 root 遠端登入
	> Remove test database and access to it? [Y/n] 
	# 移除 test 資料表
	> Reload privilege tables now? [Y/n] 
	# 重新載入資料表權限
	```

3. MySQL 的啟動，重啟，停止

	```
	$ mysql.server start
	$ mysql.server restart
	$ mysql.server stop
	```

## 在 Mac 上更新 MySQL

1. 利用 brew 進行更新，更新後會預設一個不用輸入密碼的 root 帳號

	```
	$ brew upgrade mysql
	```

2. 修改 root 密碼，可以參考上述的方法

3. 舊有資料結構更新
由於不同版本的 MySQL，可能會有不一樣的資料結構，導致新版無法使用舊的資料。可以使用 mysql_upgrade 對資料進行更新
	 
	```
	mysql_upgrade -u root -p  --force 
	```

## 其他問題

### MySQL Handling of GROUP BY

only_full_group_by (Default in mysql 5.7.9) 

SQL92 and earlier does not permit queries for which the select list, HAVING condition, or ORDER BY list refer to nonaggregated columns that are neither named in the GROUP BY clause nor are functionally dependent on (uniquely determined by) GROUP BY columns.

以下面的例子來說，如果 `name` 是 primary key 或是 unique NOT NULL column，GROUP 時 `address` 可以對映到唯一 `name`。反之，將造成一個 address 會找到超過一個 `name` ，這種情況（nonaggregated columns）是被禁止的。

```
mysql> SELECT name, address, MAX(age) FROM t GROUP BY name;
> ERROR 1055 (42000): Expression #2 of SELECT list is not in GROUP
BY clause and contains nonaggregated column 'mydb.t.address' which
is not functionally dependent on columns in GROUP BY clause; this
is incompatible with sql_mode=only_full_group_by
```

* 解法一：ANY_VALUE()

```
mysql> SELECT name, ANY_VALUE(address), MAX(age) FROM t GROUP BY name;
```

* 解法二：關閉 ONLY_FULL_GROUP_BY mode

```
mysql> set global sql_mode='STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION';
mysql> set session sql_mode='STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION';
```

> Note.

一對多的資料，展開後會出現多筆，但只要回傳一筆，原本的版本可以對 id 進行 GROUP。但是新版的 MYSQL 禁止這種 GROUP 0.0"

## Reference

[1] [brew install mysql on mac os](http://stackoverflow.com/questions/4359131/brew-install-mysql-on-mac-os)
[3] [MySQL常用指令及帳戶管理](http://itzone.hk/article/article.php?aid=200406230146464878)
[2] [MySQL Server 安裝後的設定](http://blog.ilc.edu.tw/blog/blog/25793/trackbacks/427683)
[4] [升級 MySQL 完成後, 建議手動執行的命令](https://blog.longwin.com.tw/2010/10/mysql-upgrade-cmd-linux-2010/)
[5] [mysql log error](http://missions5.blogspot.tw/2015/06/mysql-log-error.html)
[6] [https://github.com/munkireport/munkireport-php/issues/351](https://github.com/munkireport/munkireport-php/issues/351#issuecomment-159391827)

---
## License

<img src="http://i.creativecommons.org/l/by-sa/3.0/88x31.png" style="    margin: 0;">
本著作由[Chang Wei-Yaun (v123582)](https://www.facebook.com/v123582)製作，
以[創用CC 姓名標示-相同方式分享 3.0 Unported](http://creativecommons.org/licenses/by-sa/3.0/deed.zh_TW)授權條款釋出。