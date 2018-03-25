# TRUNK Html Guide

## 概要
基本的にgoogleのコーディング規約に則る
TURNKはテンプレートエンジンである`slim`でマークアップしていく。
[google公式のガイド](https://google.github.io/styleguide/htmlcssguide.html)


## 目次
 1. [プロトコル](#protocol)
 1. [インデント](#indent)
 1. [大文字/小文字](#text_size)
 1. [HTMLクォーテーション](#quotes_html)
 1. [type属性](#type)

<h2 id="validate">HTTPSプロトコル</h2>

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

<h2 id="indent">インデント</h2>

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


<h2 id="text_size">大文字/小文字</h2>

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


<h2 id="quotes_html">HTMLクォーテーション</h2>

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

<h2 id="type">type属性</h2>

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
