# TRUNK Html Guide

## 概要
- 基本的にgoogleのコーディング規約に則る

## フォーマット
- TURNKはテンプレートエンジンである`slim`でマークアップしていく。
- [google公式のガイド](https://google.github.io/styleguide/htmlcssguide.html)


## 目次
 1. [プロトコル](#protocol)
 1. [インデント](#indent)
 1. [大文字/小文字](#text_size)
 1. [HTMLクォーテーション](#quotes_html)
 1. [type属性](#type)
 1. [ymlのルール](#yml)
 1. [画像の指定方法](#image_tag)


## フォーマット

<h3 id="validate">HTTPSプロトコル</h3>

- 埋め込みリソースにはHTTPSプロトコルを使用する。※可能な限り

```
<NG>
<!-- プロトコルを省略 -->
<script src="//ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.min.js"></script>

<!-- HTTPプロトコルを使用 -->
<script src="http://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.min.js"></script>

<OK>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.min.js"></script>
```

***

<h3 id="indent">インデント</h3>

- インデントはスペース2つとする。タブを使用する場合はエディターなどの設定を「2」に設定すること。
- そもそもslimを使う場合はインデントがずれると壊滅するので、注意が必要。

```
<NG>

<!-- slim -->
.sample
    .sample
      | hogehoge
     .sample

<OK>
.sample
  .sample
    | hogehoge

```


***


<h3 id="text_size">大文字/小文字</h3>

- 小文字のみを使用する。
- HTML要素名、属性、属性値 ※`art`などの文字列は除く

```
<NG>
A.sample HREF="#"
IMG SRC="images/google.png" alt="google"

<OK>
a.sample href="/"
img src="images/google.png" alt="google"
```


***


<h3 id="quotes_html">HTMLクォーテーション</h3>

- 属性値を引用するときは、ダブルクォーテーション（二重引用符）を使用する。
- 属性値の前後にはシングルクォーテーション（ ' ）ではなく、ダブルクォーテーション（ " ）を推奨する。

```
<NG>
a href='#'
img src'images/google.png' alt='google'

<OK>
a href="#"
img src"images/google.png" alt="google"
```

***

<h3 id="type">type属性</h3>

- typeスタイルシートとスクリプトの属性を省略します。
- typeスタイルシート（CSSを使用しない限り）とスクリプト（JavaScriptを使用していない場合を除く）には属性を使用しない。

```
<NG>
link rel="stylesheet" href="./stylesheet/common.css" type="text/css"
script src="js/main.js" type="text/javascript"

<OK>
link rel="stylesheet" href="./stylesheet/common.css"
script src="js/main.js"
```

***

## slim

<h3 id="yml">ymlのルール</h3>

- 命名ルール小文字始まりで、単語は「_」で区切る
- `= t('hoge.hoge')`で呼び出す

1部の構造
- commons
  - mail
  - meta
  - gender
  - button
  - devise
  - enums
  - date
  - datetime
  - errors
  - helpers
  - number
  - support
  - time
- parts
  - notice
  - job_types
  - consult
  - text
  - skils
  - menu
  - messages
  - pagination
  - user_flow
- pages
  - company
  - timeline
  - training
  - intern
  - job
  - dashbord
  - resume
  - firm
    - firm_account
  - form
    - career
    - save_changes
  - lp
    - camp
    - bootcamp
    - carrier
  - tutorial
  - thanks
  - error
- activerecord
  - errors
  - models
  - attributes

例)

```
.sample
  = t('hoge.hoge')
```

***

<h3 id="image_tag">画像の読み込み(image_tag)</h3>

- `img`タグは使わない
- `image_tag`で指定する
- サイズを指定したい場合は`size: "〇〇x〇〇"`で指定する
- `alt`は必ずつける `alt`が必要でない画像の場合は`alt=""`と指定する

例)

```
/* DBなどサーバーから取得するものなど */
.sample
  = image_tag student.secure_icon, size: "60x60"

/* 相対パスで取得するもの */
.sample
  = image_tag "camp/sample.png", alt:"sample"

/* 絶対パスで取得するもの */
.sample
  = image_tag "http://sample.png", alt:"sample", class: 'sample sample2'
```

***
