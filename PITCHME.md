# HTTP/2

---

## サーバー技術の評価軸
- サーバ負荷
- 転送データ量
- 応答性
- 設定、運用コスト

---

# HTTP/2の基本
## 登場背景

---
### 転送データは増大中
![image](assets/images/chart.png)

---
### エンドユーザーの通信速度は上昇
エンドユーザのバンド幅は年率50%で増加<br>（ニールセンの法則）<br>
![image](assets/images/nielsen-law-internet-speed-trend-curve.png)

---
### だがページロード速度は<br>通信速度に比例しない
1.6Mbpsで頭打ち<br>
![image](assets/images/latency-per-bandwidth.png)

---
### ページロードはレイテンシ(※1)が<br>小さいほど速い
![image](assets/images/loadtime-latency.png)

---
## ※1:レイテンシ
- リクエストが実施に送信されるまでの遅延時間　
-> [用語:レイテンシ](http://www.idcf.jp/words/latency.html)

---
## なぜHTTP/2か
**HTTP1.1は多重性がない**
1RTT(※2)あたり1リクエスト/レスポンスだけ<br>
緩和策は複数のTCP接続を使う<br>
-> 1RTTあたり一般的に6リクエストの制限

---
### **今までどうやってWebサイトを速く表示させてたの?**
- 昔はCSSスプライトとか
- リクエストを減らすためにファイルを統合したり (minify)
- ホスト名を変えたりとか　(`a.picspot.asia` と `b.picspot.asia` に分散させるとか)

---
### 多重性がないために複数のリクエストを必要とする
そうなると1RTT毎のレイテンシが通信速度に重くのしかかる<br>
-> そのために開発されたのが **HTTP/2** ！！！

---
## ※2:RTT
ラウンドトリップタイム
- リクエストしてからレスポンスが返るまで
![ラウンドトリップタイム](http://pds.exblog.jp/pds/1/201108/29/63/e0091163_22465544.jpg)

---
## HTTP/2とは
### 基本的な技術要素
- バイナリプロトコル
- 多重化
- ヘッダ圧縮

---
#### バイナリプロトコル
- 脆弱性を防ぐ
	- HTTP Response Splitting Attack
	- レスポンス分割攻撃
		- [HTTP レスポンス分割攻撃](http://www.asahi-net.or.jp/~wv7y-kmr/memo/php_security.html#HTTPResponseSplitting)
- 転送データ量の低減
- 全てのデータは「フレーム」に分解して送受信

---
#### 多重化
- 同時に100以上のリクエストを送信可能
- 任意のタイミングでリクエスト送信可能
- レスポンスの順序に制限なし
	- 先のレスポンスを待たないってことか

---
#### ヘッダ圧縮
- HTTP1.1のヘッダは大きい
	- リクエストで最低でも300バイト程度
	- レスポンスで通常300バイト程度
	- 100回通信するとヘッダだけで60kb

---
### HTTP1.1とHTTP2.0のやり取り簡易比較図
![1.1と2.0](https://qiita-image-store.s3.amazonaws.com/0/62386/6217ebd8-9dea-7640-24d2-115b2cafdaec.png)

---
## レスポンス優先度
- クライアントがサーバにレスポンス優先度を指定
- サーバはその優先度を参考にレスポンスを返す順番を決める
- 優先度指定することでユーザ体感速度を大幅に向上させることができる

---
## サーバプッシュ
- HTTP/2はRTTを隠蔽する技術
- でも最低1RTTはいるよね？？
	- 実は0RTTにすることができる
- それが「サーバプッシュ」
	- サーバがクライアントの発行するリクエストを予測してレスポンスをプッシュ

+++

![サーバプッシュ](http://i.yimg.jp/images/tecblog/2014-1H/http2/http2_server_push.png)

---
## 参考サイト
- [なぜ、我々はHTTP/2に対応する必要があるのか？](http://www.seojapan.com/blog/everyone-moving-http2)
- [で、 HTTP2.0 対応って何をすればいいの？](http://dskst9.hatenablog.com/entry/2016/01/30/235019)
- [HTTPとサーバ技術の最新動向](https://www.slideshare.net/kazuho/http-58452175)

---
- [bagder/http2-explained: A detailed document explaining and documenting HTTP/2, the successor to the widely popular HTTP/1.1 protocol](https://github.com/bagder/http2-explained)
- [http2 explained - The HTTP/2 book](https://daniel.haxx.se/http2/)

http2-explained の中に背景が少しだけ語られており、プロダクト開発にも通じる言葉が心に響きました。

---
## あと
- サーバーの実装方法もGithubにたくさんある、GolangやC++が多い印象
- 既存のブラウザ・サーバー設定・アプリケーション側の対応方法もGithubにサンプルある

