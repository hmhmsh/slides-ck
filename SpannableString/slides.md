## SpannableString

***

例えば、名前が複数個あるとき...

文字の途中にリンクつけたい時...

1個1個TextViewつくって、ごにょごにょして...

めんどくさいな(・ω・)

---

そこで、***SpannableString***

***

文字列を切り分けて、それぞれでClick管理ができる:stuck_out_tongue_closed_eyes:

とりあえず見てこう

***

まず、複数個の文字を1つの文字に

```
String allStr = "Aさん" + ", " + "Bさん" + ", " + "Cさん"
```

間に、コンマも打っておこう...

---

ここで登場:ghost:

```
SpannableString spannableStr = new SpannableString(allStr);
```

---

探したい文字を入れて

```
String searchStr = "Bさん"
int start = 0;
int end = 0;

Pattern pattern = Pattern.compile(searchStr);
Matcher matcher = pattern.matcher(allStr);
while (matcher.find()) {
	start = matcher.start();
	end = matcher.end();
	break;
}
```

---

見つかったら、その文字にタッチをつけるだけ

```
ClickableSpan clickableSpan = new ClickableSpan() {
	@Override
	public void onClick(View textView) {
		// 押された時の処理
	}
}
spannableStr.setSpan(clickableSpan, start, end, Spanned.SPAN_INCLUSIVE_INCLUSIVE);
```

---

ちなみに、4つ目の引数は、文字を含む等設定できます

```
// 最初も最後も含む
Spanned.SPAN_INCLUSIVE_INCLUSIVE
// 最初だけ含む
Spanned.SPAN_INCLUSIVE_EXCLUSIVE
// 最後だけ含む
Spanned.SPAN_EXCLUSIVE_INCLUSIVE
// 最初も最後も含まない
Spanned.SPAN_EXCLUSIVE_EXCLUSIVE
```

この他にもあるんですが、詳細は闇の中:bow:

---

最後にTextViewにsetします

```
textView.setText(spannableStr);
textView.setMovementMethod(LinkMovementMethod.getInstance());
```

:pushpin:2行目のMovementMethodをsetしないとタッチがきかないです
***

Thanks:heart: