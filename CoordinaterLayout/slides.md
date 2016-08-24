## Coordinaterlayout

***
## Android Design Support Library
AndroidでMaterial Designを実装するためのさまざまなコンポーネントが入っている

---

対象

```
Target -> Android 5.0 or higher (API Level 21)
Min -> Android 4.0.3 (API Level 15)
```

---

サポート機能

```
・Snackbar
・Floating Action Button
・Floating labels for editing text
・Navigation View
・Tabs
・CoordinatorLayout and etc..
・Collapsing Toolbars
```
***

## CoordinaterLayout
- Coordinator -> 調整者、まとめ役
- CoodinatorLayoutの子View同士に関係を持たせる
	- 参照先のViewが移動した場合の追従
	- 標準で参照先になれる

```
HorizontalGridView
NestedScrollView
RecyclerView
SwipeRefreshLayout
VerticalGridView
```
***

## 使い方

build.gradleに追加

```
dependencies {
    compile "com.android.support:appcompat-v7:23.1.1"
    compile "com.android.support:design:23.1.1"
}
```

---

## 階層

```
<CoordinatorLayout>
    <AppBarLayout>
        <CollapsingToolbarLayout>
            <Toolbar />
        </CollapsingToolbarLayout>
    </AppBarLayout>
    <ScrollView />
</CoordinatorLayout>
```

CoordinaterLayoutでかこむだけ:smile:
---

## 幅と高さの設定くらい:dog:

```
<?xml version="1.0" encoding="utf-8"?>
<android.support.design.widget.CoordinatorLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:fitsSystemWindows="true"
    >

    <android.support.design.widget.AppBarLayout
        android:id="@+id/app_bar"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:fitsSystemWindows="true"
        android:theme="@style/AppTheme.AppBarOverlay">
```

---

```
<android.support.design.widget.CollapsingToolbarLayout
    android:id="@+id/toolbar_layout"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:fitsSystemWindows="true"
    app:contentScrim="?attr/colorPrimary"
    app:layout_scrollFlags="scroll|enterAlwaysCollapsed">
```

これを変えるだけで挙動がいろいろできる！！
↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓↓

```
app:layout_scrollFlags="scroll|enterAlwaysCollapsed"
```
---

## enterAlwaysCollapsed

```
<android.support.design.widget.CollapsingToolbarLayout>

    <ImageView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:src="@drawable/umaru"
        android:scaleType="fitXY"
        app:layout_collapseMode="parallax"/>

    <android.support.v7.widget.Toolbar
        android:id="@+id/toolbar"
        android:layout_width="match_parent"
        android:layout_height="?attr/actionBarSize"
        app:layout_collapseMode="pin"
        app:popupTheme="@style/AppTheme.PopupOverlay">

        <ImageView/>

        <ImageView/>

    </android.support.v7.widget.Toolbar>

</android.support.design.widget.CollapsingToolbarLayout>
```

ポイント

```
app:layout_collapseMode="parallax"
app:layout_collapseMode="pin" // 残る
```

---

![a](ExitUtilCollapsed.gif)

---

## enterAlways

```
<android.support.design.widget.CollapsingToolbarLayout
    android:id="@+id/toolbar_layout"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:fitsSystemWindows="true"
    app:contentScrim="?attr/colorPrimary"
    app:layout_scrollFlags="scroll|enterAlways">
```

---

![a](EnterAlways.gif)

---

## enterAlwaysCollapsed

```
<android.support.design.widget.CollapsingToolbarLayout
    android:id="@+id/toolbar_layout"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:fitsSystemWindows="true"
    app:contentScrim="?attr/colorPrimary"
    app:layout_scrollFlags="scroll|enterAlwaysCollapsed">
```

---

![a](EnterAlwaysCollapsed.gif)

---

## 組み合わせる

```
<android.support.design.widget.CollapsingToolbarLayout
    android:id="@+id/toolbar_layout"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:fitsSystemWindows="true"
    app:contentScrim="?attr/colorPrimary"
    app:layout_scrollFlags="scroll|enterAlwaysCollapsed">

        <ImageView/>

        <android.support.v7.widget.Toolbar/>

    </android.support.design.widget.CollapsingToolbarLayout>

    <android.support.design.widget.TabLayout
        android:id="@+id/tabs"
        android:layout_width="match_parent"
        android:layout_height="?attr/actionBarSize"
        android:fitsSystemWindows="true"
        app:layout_scrollFlags="scroll|enterAlways"/>
```
---

![a](Mix.gif)

***
## Thanks!!














