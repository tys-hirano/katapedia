# RDB

## 用語

DDL：Data Definition Language データ定義言語。データを格納するための構造を定義する。

DML：Data Manipulation Language データ操作言語。定義されたデータ構造中の個々のデータを操作する。

DCL：Data Control Language データ制御言語。データへのアクセス権限などを制御する。



## 命名規則

命名規則はスネークケース(小文字で単語を_区切りにしたもの)を採用しているパターンが多い

カラム名もスネークケースを採用したほうが命名規則が統一されて美しい


* テーブル編
複数形

tlm_values


基本的にはRailsの命名規則に従うのがよいだろう


http://railsdoc.com/rails_base


## SQLite

### 使い方

http://so-zou.jp/web-app/tech/database/sqlite/


#### よく使うコマンド

.databases

.table

.dump ?TABLE?

.help

.exit


#### 利用可能な型

http://so-zou.jp/web-app/tech/database/sqlite/data/data-type.htm


## PostgreSQL

#### キャラクタ型を整数に変換する方法

~~~
ALTER TABLE cps_def ALTER COLUMN no_imaging_flag TYPE integer USING (no_imaging_flag::integer);
~~~

## MySQL

### TroubleShooting

#### ActiveRecord::StatementInvalid (Mysql2::Error: Incorrect string value:というエラーが出る

文字コードが原因。

`show table status;`

をして、

latin1_swedish_ci とかを探す。

あったら、

`ALTER TABLE my_table CONVERT TO CHARACTER SET utf8;`

をしてUTF-8にする。
