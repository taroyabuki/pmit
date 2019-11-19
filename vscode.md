# Visual Studio Codeの導入

## インストール

次のソフトウェアをインストールする。

* [VS Code](https://code.visualstudio.com/)
* [Java Runtime Environment](https://java.com/ja/download/manual.jsp)
* [Git](https://git-scm.com/downloads)

Windowsでは，Chocolateyでまとめてインストールするのが簡単（アクセス数に制限があるため，教室で大人数が一斉にインストールするのは難しい）。上のリンク先から一つずつダウンロード・インストールしてもよい（Javaは64ビット版をインストールし，インストール後に一度サインアウトする）。

Chocolateyを使う場合は，[Installing Chocolatey](https://chocolatey.org/install)の手順に従う。
概要は次のとおり。

スタートボタンを右クリックして，Windows Powershell（管理者）を起動し，以下のコマンドを実行する。

```bash
Set-ExecutionPolicy AllSigned
# 確認を求められたらY，エンター

Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))

cinst javaruntime vscode git -y
```

## VS Codeの拡張機能

`Ctrl+Shift+x`で拡張機能の検索タブを開き，キーワードを入れると該当する拡張機能が出てくる。名前を確認して、「Install」をクリックしてインストールする。

名前|キーワード|メモ（使用する講義等）
---|---|---
hexdump for VSCode|`hexdump`|講義「情報リテラシ」
W3C Validation|`w3c`|講義「情報リテラシ」，PM実験，PM演習。Windows Security Alertが出たら，アクセスを許可する。
Japanese Language Pack for Visual Studio Code|`japanese`|日本語UIが不要なら入れなくてもよい。

## VS Codeのその他の設定

- 空白文字を見やすくするために，`Ctrl+,(Comma)`で設定タブを開き，検索欄に`whitespace`と入力，Editor: Render Whitespaceを「all」にする。
- 全角空白を見やすくするために，フォントRicty Diminishedを導入する。
    - [フォントファイル](https://github.com/edihbrandon/RictyDiminished/raw/master/RictyDiminished-Regular.ttf)をダウンロードし，ダブルクリックで開き，「インストール」をクリックする。
    - VS Codeを再起動し，`Ctrl+,(Comma)`で設定タブを開き，検索欄に`font`と入力，Editor: Font Familyを「`Ricty Diminished`」にする。

VS Codeとは関係ないが，このあたりで，ファイルの拡張子が表示されるようにしておくこと。
