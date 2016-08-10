## Reveal-ck

~簡単スライドこうざぁあ~

---

大まかに言うと...***slides.md***作るだけ！

なんて簡単な←

---
必要な装備は

1. Ruby
2. ターミナル
3. テキストエディター

## だけ‼︎

***

ふむふむ...

でも、むずかしいんじゃないの？

## そんなことはないんです！
手順は、たったの4ステップ:smile:

↓
---

1. $gem install reveal-ck
2. "slides.md"ファイル作成
3. "$reveal-ck generate"
4. "$reveal-ck serve"

## これだけで、

http://localhost:10000

## にスライド完成!!

↓
---
## "$gem install reveal-ck"
ターミナルで、"$gem install reveal-ck"

reveal-ckをインストール

↓
---
## "slides.md"ファイル作成
好きなフォルダに"slides.md"ファイルを作成しましょ！

作ったら、slides.mdの中身書き書き

このスライドに大まかな機能を紹介してるので参考に

↓
---
## "$reveal-ck generate"
ターミナルでslides.mdの階層まで移動

"$reveal-ck generate"で

slidesってフォルダが自動生成

↓
---
## "$reveal-ck serve"

ターミナルで"$reveal-ck serve"を実行

そこで、http://localhost:10000をひらくと...

あら不思議！スライドができてるんです！

↓
---
## それでは、機能を大まかに
（書き方も載せてまーす）

右に進みまーす

→
***
使えるのは、

* ## 大文字

* 普通文字

* ***斜体***

* **強調**

```
<slides.mdでの書き方>

## 大文字
普通文字
***斜体***
**強調**
```
***
縦にページ移動できる

```
<slides.mdでの書き方>

＊＊＊
ページ
ーーー
次のページ
ーーー
次の次のページ
＊＊＊

```

↓
---
## リスト表示
* あ
* い
* う

```
<slides.mdでの書き方>

## リスト表示
* あ
* い
* う
```

もういっちょう！

↓
---
## 数字リスト
1. か
2. き
3. く

```
<slides.mdでの書き方>

## 数字リスト
1. か
2. き
3. く
```

次は、横です→
***
## 画像もurlで表示
![Ruby Guuide: Open](http://canadaesl.com/wp-content/uploads/2015/08/canada-toronto-ryugaku-working-holiday-english-kanji-is-so-hard-to-learn-832x350.jpg)

```
<slides.mdでの書き方>

![Ruby Guuide: Open](http://xxxx画像URLxxxx)
```

---
## コードもかけちゃう

```
- (NSString*)myName {
	return @"hmhm"
}

// -> "hmhm"
```

```
<slides.mdでの書き方>

｀｀｀
- (NSString*)myName {
	return @"hmhm"
}

// -> "hmhm"
｀｀｀

```

---
## 絵文字もつけられちゃう

:smile::heart:

:scream::joy::paw_prints::underage:

```
<slides.mdでの書き方>

## 絵文字もつけられちゃう

:smile::heart:

:scream::joy::paw_prints::underage:
```
---
## 設定もファイル1つで簡単

```
config.yml

title: "サイトのタイトル"
author: "作者名"
theme: "Black"
```
config.yml作るだけw

テーマもこんなに選べる！

```
theme: "White"
theme: "League"
theme: "Sky"
theme: "Beige"
theme: "Simple"
theme: "Serif"
theme: "Blood"
theme: "Night"
theme: "Moon"
theme: "Solarized"
```
---
## 一応、フォルダ階層を！

```
MySlide
	- slides.md
	- config.yml
	- slides
```

---
# LET`s REVEAL-CK!

