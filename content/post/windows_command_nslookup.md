---
title: "Windowsコマンドnslookup"
date: 2019-02-26T23:30:37+09:00
draft: false
categories: ["Windows"]
tags: ["Windows","command"]
---

## nslookup

Windowsコマンドの一つである ` nslookup ` はDNSによる名前解決を行うツールです。
IPアドレス(Aレコード)を正引きする場合は下記のようにする。
例) : www.yahoo.co.jpのIPアドレス

1. コマンドプロンプトを開きます。
(Windowsキー + R  またはWindows10の場合は左下の検索窓にコマンドと打つと検索結果として出てきます。)

2. nslookup www.sony.co.jp と入力して実行すると

```command:
権限のない回答 :
名前: e9538.dscx.akamaiedge.net
Address: 104.113.123.228
Aliases: www.sony.co.jp
         www.sony.co.jp.edgekey.net

```

と返答が返ってきます。

権限のない回答とはDNSサーバー自体が保持していた情報ではなく、他のDNSサーバーの情報で回答を出している状態です。

<br>

権限のある回答を得るには ` yahoo.co.jp ` のNSレコードを調べます。

<br>

調べ方は下記のようになります。

```command:
nslookup  -type=ns sony.co.jp
サーバー: UnKnown
Address: 192.168.11.1

権限のない回答:
sony.co.jp     nameserver = ns1.sony.co.jp
sony.co.jp     nameserver = ns4.sony.co.jp
sony.co.jp     nameserver = dns-a.iij.ad.jp
sony.co.jp     nameserver = ns0.sony.co.jp

ns4.sony.co.jp   internet address = 114.179.36.146
ns4.sony.co.jp   AAAA IPv6 address = 2400:4104:400::146
dns-a.iij.ad.jp  internet address = 202.232.2.16
dns-a.iij.ad.jp  internet address = 210.130.1.17
dns-a.iij.ad.jp  AAAA IPv6 address = 2001:240:bb81::2:17
dns-a.iij.ad.jp  AAAA IPv6 address = 2001:240:bb81::2:16
ns0.sony.co.jp   internet address = 211.125.138.150
ns0.sony.co.jp   AAAA IPv6 address = 2001:cf8:0:6a::150
ns1.sony.co.jp   internet address = 211.125.138.153
ns1.sony.co.jp   AAAA IPv6 address = 2001:cf8:0:6a::153

```

<br>

それから ` internet address ` のIPアドレスに下記のようにアクセスすると

<br>

```command:

nslookup
既定のサーバー: UnKnown
Address: 192.168.11.1

server 114.179.36.146
既定のサーバー: [114.179.36.146]
Address: 114.179.36.146

```

とレスポンスがあり下記のコマンドを実行すると

<br>

```command:

www.sony.co.jp
既定のサーバー: [114.179.36.146]
Address: 114.179.36.146

名前: www.sony.co.jp

```

<br>

と回答があり、` 権限のない回答 ` とはならしません。

<br>

理由は、114.179.36.146のDNSサーバにwww.sony.co.jpの情報があり尚且つnslookupコマンドで

<br>

server 指定を行い直接調べに行っているためです。



