# Visual Studio Codeの導入

## インストール

* Windowsでは，Chocolateyで入れるのが簡単。
* Windows以外、またはChocolateyを使いたくない場合は自分で調べて入れる。VS Code自体は，https://code.visualstudio.com/ からインストーラをダウンロードしてインストールできる。JREとGitも自分で入れること。

Chocolateyで入れる方法は次のとおり。（参考：）

1. スタートボタンを右クリックして，Windows Powershell（管理者）をクリックする。
1. 「`Set-ExecutionPolicy AllSigned`」と入力して，エンター。プロンプトには`Y`，エンター。
1. [Installing Chocolatey](https://chocolatey.org/install)の「Now run the following command:」に書かれているコマンドをコピー＆ペーストしてエンター。
1. 「`cinst javaruntime vscode git -y`」と入力して，エンター。（javaruntimeは後述のW3C Validatorのため）

## 拡張機能

`Ctrl+Shift+x`で拡張機能の検索タブを開き，キーワードを入れると該当する拡張機能が出てくる。名前を確認して、「Install」をクリックしてインストールする。

名前|キーワード|メモ（使用する講義等）
---|---|---
hexdump for VSCode|`hexdump`|講義「情報リテラシ」
W3C Validation|`w3c validator`|講義「情報リテラシ」，PM実験，PM演習
Japanese Language Pack for Visual Studio Code|`japanese`|日本語UIが不要なら入れなくてもよい。

## その他の設定

- 空白文字を見やすくするために，`Ctrl+,(Comma)`で設定タブを開き，検索欄に`whitespace`と入力，Editor: Render Whitespaceを「all」にする。
- 全角空白を見やすくするために，フォントRicty Diminishedを導入する。
    - [フォントファイル](https://github.com/edihbrandon/RictyDiminished/raw/master/RictyDiminished-Regular.ttf)をダウンロードし，ダブルクリックで開き，「インストール」をクリックする。
    - VS Codeを再起動し，`Ctrl+,(Comma)`で設定タブを開き，検索欄に`font`と入力，Editor: Font Familyを「`Ricty Diminished`」にする。
