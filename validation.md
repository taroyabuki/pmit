# 正しいHTML文書

## HTML文書の正しさの観点

観点|判定すべきこと
--|--
**構文**|**マークアップがHTMLの規格どおりかどうか（PM実験でこだわるのはここだけ）**
意味|マークアップの意味が作成者の意図どおりかどうか
表示|ページの表示が作成者の意図どおりかどうか
内容|ページの内容が正しいかどうか

### 補足

表示は正しいが意味は正しくない例：

```html
1. ホップ<br>
2. ステップ<br>
3. ジャンプ<br>
```

意味を正しくするためには，番号付きの箇条書きのための要素を知る必要がある．

表示と意味のどちらも正しい例：
```html
<ol>
<li>ホップ</li>
<li>ステップ</li>
<li>ジャンプ</li>
</ol>
```

## 構文のチェック方法

構文のチェックは機械的にできる．

* **（推奨） [VSCode + W3C Web Validator](vscode.md) （[解説動画](https://youtu.be/fdcs3LfjX2M)）**
* W3C Markup Validation Service
  - [URLでチェック](https://validator.w3.org/#validate_by_uri)
  - [ファイルアップロードでチェック](https://validator.w3.org/#validate_by_upload)
  - [HTMLを入力してチェック](https://validator.w3.org/#validate_by_input)
* ブラウザ上で確認する．
    - [Firefox](https://wwws.kobe-c.ac.jp/~miura/HtmlValidator/index.html)
    - [Chrome](https://chrome.google.com/webstore/detail/html-validator/mpbelhhnfhfjnaehkcnnaknldmnocglk)

補足：PM実験用の公開サーバでもチェックしている．そのチェックを自分の環境で再現する方法は次の通り．（Ubuntuの場合．WSLで試すのが簡単．）

```bash
# 準備
sudo apt update
sudo apt install -y default-jre python3-pip
pip install html5validator

# チェック
cd リポジトリのトップディレクトリ
html5validator --root htdocs/ --also-check-css
```

## 練習

次のようなHTML文書の構文エラーを修正してみよう．
エラーはVSCode上で確認することを推奨する．それができない人用→[W3C HTML Validatorの結果](https://validator.w3.org/nu/?doc=https%3A%2F%2Ftaroyabuki.github.io%2Fpmit%2Finvalid.html)

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

間違い1：「<」，「>」，「&」をそのまま使っている．（タグだと解釈されてしまう．）

```html
<<Rock & Roll>>
```

修正：「`&lt;`」，「`&gt;`」，「`&amp;`」を使う．

```html
&lt;&lt;Rock &ampl Roll&gt;&gt;
```

間違い2：使えないはずの（古い）要素を使っている．

```html
<font size="+2">こんにちは</font>
```

修正：古い参考書は書庫にしまい，古い要素の代わりになるCSSプロパティをstyle.cssに記述する．

```html
<span class="bar">こんにちは</bar>
```

```css
.bar {
  font-size: x-large;
}
```

間違い3：要素が入れ子になっていない．

```html
<div><a href="foo.html">こちら</div></a>
```

修正：タグを入れ子にする．

```html
<div><a href="foo.html">こちら</a></div>
```

すべて修正すると，構文エラーがなくなることを確認してほしい．
