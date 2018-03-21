# TRUNK Html Guide

## 概要
基本的にgoogleのコーディング規約に則る
[google公式のガイド](https://google.github.io/styleguide/htmlcssguide.html)


## 目次
 1. [プロトコル](#protocol)
 1. [インデント](#indent)

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
