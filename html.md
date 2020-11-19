# ウェブページを書く練習

ページの内容をHTMLで書き，見た目をCSSで指定する．

VS CodeでCtrl+nとして新しいファイルを作り，以下のコードを貼り付け，「index.html」というファイル名で保存する．

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

index.htmlをウェブブラウザで開く．

補足：トップページ（最初に開くページ）のファイル名はindex.htmlにしておくこと．それ以外のファイルの名前は拡張子がhtmlであれば何でもいいのだが，英単語を使うことを勧める．

VS CodeでCtrl+nとして新しいファイルを作り，以下のコードを貼り付け，「style.css」というファイル名で保存する．

```css
body {
  color: white;
  background-color: #243a5e;
}
```

ウェブブラウザのindex.htmlを開いているタブで，Ctrl+rとしてページを再読込する．

新しいページ「foo.html」を作り，index.htmlからリンクする．

1. index.htmlがあるフォルダと同じフォルダに，foo.htmlを作る（省略）．
1. index.htmlのbody要素内に，次のようなa要素を書く．

```html
新しいページは<a href="foo.html">こちら</a>．
```

VS CodeにはShift+Alt+fでHTMLを整形する便利が機能があるから，活用してほしい．
