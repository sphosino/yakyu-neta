# プロ野球 ネタ九回勝負

あだ名の由来、名場面、球場や応援のウラ話を当てる、一人用のプロ野球ネタゲームです。点数よりも「誰かに話したくなるネタ」を拾うことが目的です。

**ここで遊べます → https://sphosino.github.io/yakyu-neta/**

`index.html` をダウンロードしてブラウザで開いても、そのまま遊べます。

## 遊び方

1. 「ごちゃまぜ」「あだ名で勝負」「名場面・球場・ウラ話」から選ぶ
2. 1イニングにつき1ネタ。「誰のあだ名？」「由来はどれ？」「ホント？ウソ？」のどれかに答える。正解で1点
3. 答えると由来の話と「話のタネ」が出る。知らなかったら「へぇ〜」を押す
4. 9回が終わると、スコアと「今日の話のタネ帳」が出る

点線の付いた言葉はタップすると意味が出ます。右上の「用語集」からも引けます。

## 中身

- ネタ：43個（あだ名24・名場面8・球場/応援7・ウラ話4）
- 用語集：105語（野球のことば、大会・リーグ・球場、人物、時代・文化）

ネタはすべて `index.html` の中の配列 `D` に入っています。1ネタは次の形です。

```js
{g:"あだ名", nick:"ギータ", name:"柳田悠岐", f:"origin",
 q:"問題文", opts:["正解","ハズレ","ハズレ"], ans:0,
 story:"由来の話", tane:"話のタネ（一言）"}
```

- `g`：ジャンル（あだ名／名場面／球場・応援／ウラ話）
- `f`：問題の形式（`who`＝誰？、`origin`＝どれ？、`tf`＝ホント？ウソ？。`tf` のときは `opts` の代わりに `tf:true/false`）
- 用語集は配列の下の `GLOSS` に、カテゴリごとに入っています。ここに足した言葉は、本文に出てきたときに自動でタップできるようになります。

## 出典

由来や経緯は、報道や資料で確認できたものだけを入れています。主な出典は次のとおりです。

- 各選手・出来事の Wikipedia 日本語版（佐々木主浩、宮田征典、中村剛也、小川泰弘、三浦大輔、内藤尚行、城之内邦雄、黒木知宏、T-岡田、パンチ佐藤、大久保博元、村田兆治、金本知憲、カーネル・サンダースの呪い、バックスクリーン3連発、10.19、10.8決戦、ジェット風船、江川事件、ラッキーセブン、ビールかけ）
- [松井秀喜さんがゴジラと呼ばれた日](http://www.henshin-hero.com/archives/25357775.html)
- [G.G.佐藤、“G.G.”の由来明かす（マイナビ）](https://news.mynavi.jp/article/20240326-2914042/)
- [ノムさん名言「月見草」誕生秘話（野球太郎）](https://yakyutaro.jp/r.php?hash=2K0e5)
- [「ギータ」誕生の瞬間（週刊ベースボール）](https://column.sp.baseball.findfriends.jp/?id=046-20200210-02&pid=column_detail)
- [「神様、仏様、稲尾様」に新説（西スポWEB OTTO!）](https://nishispo.nishinippon.co.jp/article/787291)
- [川上哲治は赤バットを戦前から使っていた（週刊ベースボール）](https://column.sp.baseball.findfriends.jp/?pid=column_detail&id=097-20180603-10)
- [斎藤佑樹「ハンカチ王子と呼ばれるのは好きではなかった」（Sportiva）](https://sportiva.shueisha.co.jp/clm/baseball/npb/2022/09/18/post_228/)
- [流行語大賞「村神様」の元祖とは（二宮清純コラム）](https://www2.myjcom.jp/npb/column/20221209.shtml)
- [衣笠祥雄、壮絶なる“鉄人伝説”（二宮清純コラム）](https://www2.myjcom.jp/npb/column/20250228.shtml)
- [新庄剛志氏が「宇宙人の名付け親」野村克也氏に感謝（Full-Count）](https://full-count.jp/2020/02/11/post686607/)
- [検疫で海に捨てられた聖地の土（沖縄タイムス）](https://www.okinawatimes.co.jp/articles/-/1655632) / [首里高校に甲子園の小石を届けたCA（QAB）](https://www.qab.co.jp/news/20221031157329.html)
- [巨人・闘魂こめて！阪神・六甲おろし！共に古関裕而の名曲（福島民友）](https://www.minyu-net.com/serial/koseki/FM20200622-509537.php)
- [天覧試合に始まった阪神・村山実の反骨（週刊ベースボール）](https://column.sp.baseball.findfriends.jp/?pid=column_detail&id=097-20200407-10)
- [新庄氏 伝説の敬遠球サヨナラ打を振り返る（デイリー）](https://www.daily.co.jp/tigers/2020/04/10/0013260926.shtml)
- [東京ドームの屋根は空気で支えられている?（建設技術図鑑）](https://kensetsu.profile-partner.info/guide/tokyo-dome-air-supported-membrane.html)
- [荒川博氏逝去 王貞治の一本足を作り上げた異常な練習（デイリー新潮）](https://www.dailyshincho.jp/article/2016/12160557/?all=1)
- [8球団が競合した野茂英雄（週刊ベースボール）](https://column.sp.baseball.findfriends.jp/?pid=column_detail&id=097-20221019-10)
- [古田敦也が明かす「代打、オレ」秘話（アサ芸）](https://www.asagei.com/excerpt/331734)
- [甲子園秘話（阪神甲子園球場公式）](https://koshien.hanshin.co.jp/history/trivia.html)
- [我が巨人軍は永久に不滅です（ピクシブ百科事典）](https://dic.pixiv.net/a/%E6%88%91%E3%81%8C%E5%B7%A8%E4%BA%BA%E8%BB%8D%E3%81%AF%E6%B0%B8%E4%B9%85%E3%81%AB%E4%B8%8D%E6%BB%85%E3%81%A7%E3%81%99)
