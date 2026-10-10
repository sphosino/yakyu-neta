# プロ野球 ネタ九回勝負

あだ名の由来、名場面、球場や応援のウラ話を当てる、一人用のプロ野球ネタゲームです。点数よりも「誰かに話したくなるネタ」を拾うことが目的です。

**ここで遊べます → https://sphosino.github.io/yakyu-neta/**

`index.html` をダウンロードしてブラウザで開いても、そのまま遊べます。

## 遊び方

1. ホーム画面で遊び方を選ぶ
   - **今日は何の日**：今日の日付（なければ一番近い日付）に起きた出来事から試合開始
   - **ごちゃまぜ**：全ネタからランダムに9つ
   - **つながりモード**：同じ人物・球場・球団でつながるネタを、芋づる式にたどる
   - **相手に合わせる**：話す相手の好きな球団と世代を選ぶと、刺さりそうなネタを優先して出す
   - **ジャンルで選ぶ**：あだ名／名場面／球場・応援／助っ人・球団・ウラ話
2. 1イニングにつき1ネタ。「誰？」「どれ？」「ホント？ウソ？」のどれかに答える。正解で1点
3. 答えると、由来の話・「話のタネ」・そのまま使える「切り出し方」の一言が出る。知らなかったら「へぇ〜」を押す
4. 9回が終わると、スコアと「今日の話のタネ帳」が出る。タネ帳はコピーして LINE などに貼れる

一度出会ったネタは**ネタ図鑑**（右上）に集まります。選手や監督の名前（実線の下線）をタップすると**人物カード**が開き、プロフィールと、このゲームに出てくるその人の話が見られます。記録はそのブラウザに保存されます。点線の付いた言葉はタップすると意味が出て、「用語集」からも引けます。

## 中身

- `index.html`：ゲーム本体
- `neta.js`：ネタ（100個。名場面44・あだ名24・球場/応援9・ウラ話9・球団/背番号8・助っ人6。うち59個が日付つきで、1〜12月すべてに出来事がある）
- `people.js`：人物カード（選手・監督61人）。`aka` に呼び方（「ノムさん」「マー君」など）を入れておくと、その呼び方でもタップできる
- `gloss.js`：用語集（182語）。ここに足した言葉は、本文に出てきたときに自動でタップできるようになる

### ネタの足し方

`neta.js` の配列 `NETA` に1件足すだけです。

```js
{"id":"gita",              // 図鑑の記録に使う、ほかと重ならない英数字
 "g":"あだ名",              // ジャンル
 "nick":"ギータ",           // 見出し
 "name":"柳田悠岐",          // 誰・いつ・どこ
 "y":2011,                  // 年（「相手に合わせる」の世代判定に使う）
 "date":"10-12",            // 出来事の月日（任意。「今日は何の日」に使う）
 "teams":["H"],             // 関係する球団（下の記号）
 "tags":["柳田悠岐","川崎宗則"], // 人物・球場など。同じタグのネタが「つながり」になる
 "f":"origin",              // who＝誰？ / origin＝どれ？ / tf＝ホント？ウソ？
 "q":"問題文",
 "opts":["正解","ハズレ","ハズレ"], "ans":0,   // tf のときは代わりに "tf":true か false
 "story":"由来の話",
 "tane":"話のタネ（一言）",
 "open":"話の切り出し方（話し言葉の一言目）"}
```

球団の記号：G巨人 T阪神 D中日 C広島 Sヤクルト DB横浜DeNA H福岡ソフトバンク L埼玉西武 Bsオリックス Mロッテ F日本ハム E楽天（前身の球団も同じ記号。近鉄はBs、南海・ダイエーはH）

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
- [明徳義塾対星稜 松井秀喜5打席連続敬遠／沢村栄治／江夏の21球／黒沢俊夫／ラッキーゾーン／中日ドラゴンズ／広島東洋カープ／ラルフ・ブライアント／ロベルト・ペタジーニ／ボブ・ホーナー／タフィ・ローズ／アレックス・ラミレス／江夏豊（Wikipedia 日本語版）](https://ja.wikipedia.org/)
- [球界再編とストライキ（Number）](https://number.bunshun.jp/articles/-/866391)
- [1996年オールスター、投手イチロー（BASEBALL KING）](https://baseballking.jp/ns/column/152233)
- [松坂大輔とイチローの初対決（Number）](https://number.bunshun.jp/articles/-/848907) / [「自信が確信に」（Number）](https://number.bunshun.jp/articles/-/839928)
- [延長17回、250球（Sportiva）](https://sportiva.shueisha.co.jp/clm/baseball/hs_other/2018/06/17/pl17_split/)
- [憧れるのをやめましょう（現代ビジネス）](https://gendai.media/articles/-/107921)
- [ホームラン記念日](https://bestcalendar.jp/dates/kinenbi/3618) / [国民栄誉賞の始まり（Forbes JAPAN）](https://forbesjapan.com/articles/detail/50095)
- [西武ライオンズのレオと手塚治虫（BASEBALL KING）](https://baseballking.jp/ns/572581/)
- [東京音頭は丸の内音頭だった（HugKum）](https://hugkum.sho.jp/609664) / [ヤクルト傘応援の岡田正泰さん（文春オンライン）](https://bunshun.jp/articles/-/54724)
- [野茂英雄／落合博満／黒田博樹／大谷翔平／佐々木朗希／槙原寛己／村上雅則／第88回全国高等学校野球選手権大会（Wikipedia 日本語版）](https://ja.wikipedia.org/)
- [プロ野球誕生の日](https://bestcalendar.jp/dates/kinenbi/5134) / [プロ野球の日](https://bestcalendar.jp/dates/kinenbi/1142)
- [2月1日キャンプインの理由（J-CAST）](https://www.j-cast.com/2019/02/01349485.html?p=all)
- [黒田博樹の広島復帰（現代ビジネス）](https://gendai.media/articles/-/41816)
- [がんばろうKOBEとオリックス（文春オンライン）](https://bunshun.jp/articles/-/5891)
- [2006年WBC決勝（NPB）](https://npb.jp/wbc/2006/score_fn.html) / [第1回WBCプレーバック（SPREAD）](https://spread-sports.jp/archives/177290/2)
- [2009年WBC決勝（AFPBB）](https://www.afpbb.com/articles/-/2585675) / [イチローの決勝打（ベースボールチャンネル）](https://www.baseballchannel.jp/wbc/28447/9/)
- [イチロー引退会見（文春オンライン）](https://bunshun.jp/articles/-/11164)
- [早実−駒大苫小牧 決勝再試合（ベースボールチャンネル）](https://www.baseballchannel.jp/etc/285064/)
- [ライオンと野球（ライオン株式会社）](https://www.lion.co.jp/ja/company/history/museum/05/01.php)
- [小林繁、移籍1年目の巨人戦8勝0敗（デイリー）](https://www.daily.co.jp/tigers/2020/04/25/0013296155.shtml) / [村上宗隆、ホワイトソックスと契約（デイリー）](https://www.daily.co.jp/mlb/2025/12/22/0019840087.shtml) / [田中将大、巨人入団（デイリー）](https://www.daily.co.jp/baseball/2024/12/25/0018482074.shtml)
- [2007年・2013年・2024年の日本シリーズ／1959年の日本シリーズ／金本知憲／衣笠祥雄／川上哲治／村山実／村田兆治／トリプルスリー／新庄剛志／古田敦也／藤村富美男／小川泰弘／稲尾和久／田淵幸一（Wikipedia 日本語版）](https://ja.wikipedia.org/)
