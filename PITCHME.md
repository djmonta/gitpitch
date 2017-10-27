# <span style="color:#e49436">Google App Script</span> & <span style="color:#e49436">LINE bot</span>
<span style="font-size:0.9rem">〜簡単なサンプルを添えて〜</span>

---

## LINE Notify & LINE Login
[LINE Developers](https://developers.line.me/ja/)

---

### LINE Login
iOS, Android, Webアプリに組み込める
Facebookログインとか同じような仕組みはよく使われているので、ユーザーには馴染みやすい

---

### Line Notify

[LINE Notify](https://notify-bot.line.me/ja/)
サービスを登録すれば通知を送ることができる。<br>
Githubとの連携も簡単。私はIFTTTから使っていた

---

## Google App Script
Javascriptで記述<br>
Google Spreadsheetに記録したり、Gmailからメール送信したり、Googleの他サービスとの連携が簡単。<br>
トリガーを指定して関数呼び出しを設定できる

+++

### Google Spreadsheet

`=IMPORTXML("https://en.wikipedia.org/wiki/Moon_landing", "//a/@href")`

XPathを指定して、Webページの一部をスプレッドシートに挿入できる<br>
自動更新で、最低1日1回は更新される。どうやらWebサイトが更新されたら、わりと早めに反映される (実感)<br>
他にも、 `IMPORTHTML` や `IMAGE(url)` などの関数がある

---

## たとえば

Google Spreadsheet & LINE Messaging API (developer) で毎日Webサイトの情報を配信するとか<br>
LINE botからボタンポチポチで勤怠管理とか [HATARA CLOCK](http://tech-portfolio.org/)

+++

## 参考に

- [Google Apps Scriptを使い日々のコピペ作業から解放できた話 - Qiita](https://qiita.com/moonstruckdrops@github/items/d791bc7f0b7a2c2e6b5d)
- [SpreadSheetでスクレイピング。Importxml他、便利な関数9+1 - Qiita](https://qiita.com/ktmg/items/d53440c913e20f8bb34c)
- [Treasure DataとGoogleスプレッドシートで作るお手軽KPIダッシュボード - Qiita](https://qiita.com/highwide/items/9a75428e8e8bda0325db)