## Closure
~Swiftだと簡単！？~
***
みなさん知っての通りすでに標準で使われている

画面遷移完了時

```
[self presentViewController:viewController animated:YES completion:^{


}];
```

他の例がみつからない...ので、とりあえず...
---
## Closure使用可能
* 関数型言語（Scala、Haskell、OCamlなど）
* Smalltalkに由来するオブジェクト指向言語
* C# 3.0
* C++11
* ECMAScript（JavaScriptを含む）
* Groovy
* Java 8
* Perl
* Python
* Ruby
* Objective-C(Block....うん...)
* Swift（よくできてる）
***
## Objective-Cなんて...
![Ruby Guide: Open](http://blogs.c.yimg.jp/res/blog-00-0f/rip3slyme/folder/1204678/04/39095404/img_0?1399960469)
***
## 一応、Block
aとbの値見て、aの方が大きかったらYESを返すだけ...

```
- (void)viewDidLoad {
	[self closure:^BOOL(int a, int b){
		return a > b;
	}];
}

-(void)closure:(BOOL(^)(int, int))close {
	NSLog(@"%@", (close(4,2) == 1 ? @"YES" : @"NO");
}

// -> YES
```
---

なんで、メソッドの定義と呼び出し側で順番違うのw
![Ruby Guuide: Open](http://canadaesl.com/wp-content/uploads/2015/08/canada-toronto-ryugaku-working-holiday-english-kanji-is-so-hard-to-learn-832x350.jpg)

***
## Swiftを見てみよう:smile:

![Ruby Guide: Open](http://www.suzuki.co.uk/cars/configurator/uploads/equipment/image_big/thumb/original/Swift_Web_Resize_CoolWhitePearlMetallic-0.png)
***
```
override func viewDidLoad() {
	closure({ (a: Int, b: Int) -> Bool in
		return a > b
	})
}

func closure(close:(Int, Int)->Bool) {
	print("\(close(4, 2))")
}
```
print()って簡単だなぁ....あ、ちがう‼︎
---
メソッドの定義と呼び出し側の順番一緒じゃん:heart:

![Ruby Guide: Open](http://iiko-movie.com/index/img/img.jpg)
---
Swiftならもうちょいいけそう‼︎

***Trailing Closures***ってのでカッコの外にだして...

```
closure() { (a: Int, b: Int) -> Bool in
	return a > b
}
```

**型推論**で引数の型もいらないし、

返り値の型もreturnもいらないでしょ...

```
closure() { (a, b) in
	a > b
}
```
---
**ショートハンド引数名**で、

引数って（$0, $1..）に省略できるんだ...

```
closure({
	$0 > $1
})
```
ん!?

**オペレータ関数**で、

$0とか$1って勝手に判断してくれるらしいぞ...

```
closure(>)
```
***
## :zap: イミフメイ :zap:
Swift兄さん、やりすぎですよ....

![Ruby Guide: Open](http://cdn-ak.f.st-hatena.com/images/fotolife/r/room_42/20091007/20091007033139.jpg)

***<***と***>***がここまで省略できるらしいけど...

ってことは‼︎
***
***map, filterとかは...***
---
と、思ったけど

さすがにそこまで省略できなかった...

```
let channels = [ "nhk", "日テレ", "フジ" ]
channels.map { "#" + $0 }

// -> ["#nhk", "#日テレ", "#フジ"]
```
***
# Thanks!

