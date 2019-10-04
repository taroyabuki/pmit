# PM実験でやること（技術編）演習

1. ウェブページの作成
1. ウェブページの公開

参考書：大藤幹ほか『HTML+CSSデザイン 基本原則、これだけ。』（MdN, 2013）（各研究室にある。熟読はしなくていいが，全ページをめくってみることを勧める。たとえば，「PCでもスマホでも快適に読めるようにするための技術」が**ある**ことは知っておくといい。具体的にどうするかは，必要になったときに勉強する。）

## ウェブページの作成

* [Visual Studio Codeの導入](vscode.md)

### ウェブページの書き方

ページの内容をHTMLで書き，見た目をCSSで指定する。

VS CodeでCtrl+nとして新しいファイルを作り，以下のコードを貼り付け，「index.html」というファイル名で保存する。

```html
<!DOCTYPE html>
<html lang='ja'>
  <head>
    <meta charset='utf-8' />
    <link rel='stylesheet' href='style.css' />
    <title>テンプレ</title>
  </head>
  <body>
  こんにちは
  </body>
</html>
```

index.htmlをウェブブラウザで開く。

VS CodeでCtrl+nとして新しいファイルを作り，以下のコードを貼り付け，「style.css」というファイル名で保存する。

```css
body {
  color: white;
  background-color: #243a5e;
}
```

ウェブブラウザのindex.htmlを開いているタブで，Ctrl+rとしてページを再読込する。

新しいページ「foo.html」を作り，index.htmlからリンクする。

1. index.htmlがあるフォルダと同じフォルダに，foo.htmlを作る（省略）。
1. index.htmlのbody要素内に，次のようなa要素を書く。

```html
新しいページは<a href="foo.html">こちら</a>。
```

### 文法的に正しいHTMLとCSSを書く

**最終成果物のHTMLとCSSに文法エラーがあってはいけない！**

VS Codeに拡張機能W3C Validationを入れておくと，エラーの部分に赤い波線が引かれるようになる。
それを無視しないように。

Shift+Alt+fでHTMLを整形する機能も便利である。

**次のようなHTMLをVS Codeで作成し，エラーが検出されることを確認，エラーを修正せよ。**

```html
<!DOCTYPE html>
<html lang='ja'>
<head>
  <meta charset='utf-8' />
  <link rel='stylesheet' href='style.css' />
  <title>テンプレ</title>
</head>
<body>
  <h1><<Rock & Roll>></h1>
  <font size="+2">こんにちは</font>
  <div><a href="foo.html">こちら</div></a>へ
</body>
</html>
```

間違い1：「<」，「>」，「&」をそのまま使っている。（タグだと解釈されてしまう。）

```html
<<Rock & Roll>>
```

修正：「`&lt;`」，「`&gt;`」，「`&amp;`」を使う。

```html
&lt;&lt;Rock &ampl Roll&gt;&gt;
```

間違い2：使えないはずの（古い）要素を使っている。

```html
<font size="+2">こんにちは</font>
```

修正：古い参考書は書庫にしまい，古い要素の代わりになるCSSプロパティをstyle.cssに記述する。

```html
<span class="bar">こんにちは</bar>
```

```css
.bar {
  font-size: x-large;
}
```

間違い3：要素が入れ子になっていない。

```html
<div><a href="foo.html">こちら</div></a>
```

修正：タグを入れ子にする。

```html
<div><a href="foo.html">こちら</a></div>
```

## ウェブページの公開

### 準備

メンバ全員のGitHubアカウントをPMがまとめて矢吹（taro.yabuki+github@it-chiba.ac.jp）に報告する。報告の形式は以下の通り。（1行に1件，半角カンマ区切り）

```
研究室・グループ名
名前1,学生番号1,メアド1,本人のGitHubのプロフィールページ1
名前2,学生番号2,メアド2,本人のGitHubのプロフィールページ2
```

- グループ名は`矢吹研A`などでよい。
- 本人のGitHubのプロフィールページは，https://github.com/ユーザ名 という形式になる（例：https://github.com/taroyabuki ）。アクセスできることを確認してから報告すること。

### ウェブサイトを公開する方法

前提：VS Codeをインストールしたときに，Gitもインストールしていること

各チームのGitHubリポジトリにファイルを登録する。Visual Studio Codeで実行する方法については，「VS CodeでGitHubを使う」(git.mdを参照。

1. 作業用のフォルダを作る。（例：c:/work）
1. エクスプローラでそのフォルダを開き，アドレス欄に「`powershell`」と入力する。（コマンド入力用のウィンドウが現れる。PowerShellを起動して，「`c:`」エンター，「`cd /work`」エンターでもよい。）
1. 「`git clone https://github.com/yabukilab/{チーム名}.git`」を実行する。`{チーム名}`の部分は，矢吹研Aなら`yabuki-a`。（フォルダができる。例：yabuki-a）
1. 上でできたフォルダの中に，htdocsというフォルダを作る。公開するファイルはすべてその中に格納する。
1. トップページはindex.htmlとする。これは特別なファイルで，ファイル名を指定せずにアクセスできる。（例：http://yabukia.pm-chiba.tech/ にアクセスすると，リポジトリhttps://github.com/yabukilab/yabuki-a のhtdocs/index.htmlを閲覧することになる。）
1. 変更したファイルをステージ，コミット，プッシュする。
1. ウェブサイトを確認する。

各班のリポジトリは次のとおり。

- https://github.com/yabukilab/shimoda-a
- https://github.com/yabukilab/shimoda-b
- https://github.com/yabukilab/shimoda-c
- https://github.com/yabukilab/ogasawara-a
- https://github.com/yabukilab/ogasawara-b
- https://github.com/yabukilab/ogasawara-c
- https://github.com/yabukilab/yabuki-a
- https://github.com/yabukilab/yabuki-b
- https://github.com/yabukilab/yabuki-c
- https://github.com/yabukilab/takuma-a
- https://github.com/yabukilab/takuma-b
- https://github.com/yabukilab/takuma-c

各班のウェブサイトは次のとおり。

班|URL|エラーチェック
-|-|-
下田A|http://shimodaa.pm-chiba.tech/|[実行](https://validator.w3.org/nu/?doc=http%3A%2F%2Fshimodaa.pm-chiba.tech%2F)
下田B|http://shimodab.pm-chiba.tech/|[実行](https://validator.w3.org/nu/?doc=http%3A%2F%2Fshimodab.pm-chiba.tech%2F)
下田C|http://shimodac.pm-chiba.tech/|[実行](https://validator.w3.org/nu/?doc=http%3A%2F%2Fshimodac.pm-chiba.tech%2F)
小笠原A|http://ogasawaraa.pm-chiba.tech/|[実行](https://validator.w3.org/nu/?doc=http%3A%2F%2Fogasawaraa.pm-chiba.tech%2F)
小笠原B|http://ogasawarab.pm-chiba.tech/|[実行](https://validator.w3.org/nu/?doc=http%3A%2F%2Fogasawarab.pm-chiba.tech%2F)
小笠原C|http://ogasawarac.pm-chiba.tech/|[実行](https://validator.w3.org/nu/?doc=http%3A%2F%2Fogasawarac.pm-chiba.tech%2F)
矢吹A|http://yabukia.pm-chiba.tech/|[実行](https://validator.w3.org/nu/?doc=http%3A%2F%2Fyabukia.pm-chiba.tech%2F)
矢吹B|http://yabukib.pm-chiba.tech/|[実行](https://validator.w3.org/nu/?doc=http%3A%2F%2Fyabukib.pm-chiba.tech%2F)
矢吹C|http://yabukic.pm-chiba.tech/|[実行](https://validator.w3.org/nu/?doc=http%3A%2F%2Fyabukic.pm-chiba.tech%2F)
田隈A|http://takumaa.pm-chiba.tech/|[実行](https://validator.w3.org/nu/?doc=http%3A%2F%2Ftakumaa.pm-chiba.tech%2F)
田隈B|http://takumab.pm-chiba.tech/|[実行](https://validator.w3.org/nu/?doc=http%3A%2F%2Ftakumab.pm-chiba.tech%2F)
田隈C|http://takumac.pm-chiba.tech/|[実行](https://validator.w3.org/nu/?doc=http%3A%2F%2Ftakumac.pm-chiba.tech%2F)

上のエラーチェックの対象はトップページ（index.html）だけだが，他のページにもHTMLがないようにすること。
