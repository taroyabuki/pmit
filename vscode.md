# VSCode（Visual Studio Code）の導入

## インストール

次のソフトウェアをインストールする。

1. [VSCode](https://code.visualstudio.com/)
1. [Java Runtime Environment](https://java.com/ja/download/manual.jsp)**「Windows オフライン (64ビット)」をインストールし，インストール後に一度サインアウトする．**
1. [Git](https://git-scm.com/downloads)

## VSCodeの拡張機能

`Ctrl+Shift+x`で拡張機能の検索タブを開き，キーワードを入れると該当する拡張機能が出てくる。名前を確認して、「Install」をクリックしてインストールする。

名前|キーワード|メモ（使用する講義等）
---|---|---
hexdump for VSCode|`hexdump`|講義「情報リテラシ」
W3C Validation|`w3c`|講義「情報リテラシ」，PM実験，PM演習。Windows Security Alertが出たら，アクセスを許可する。
Japanese Language Pack for Visual Studio Code|`japanese`|日本語UIが不要なら入れなくてもよい。

## VSCodeのその他の設定

- 空白文字を見やすくするために，`Ctrl+,(Comma)`で設定タブを開き，検索欄に`whitespace`と入力，Editor: Render Whitespaceを「all」にする。
- 全角空白を見やすくするために，フォントRicty Diminishedを導入する。
    - [フォントファイル](https://github.com/edihbrandon/RictyDiminished/raw/master/RictyDiminished-Regular.ttf)をダウンロードし，ダブルクリックで開き，「インストール」をクリックする。
    - VSCodeを再起動し，`Ctrl+,(Comma)`で設定タブを開き，検索欄に`font`と入力，Editor: Font Familyを「`Ricty Diminished`」にする。

VSCodeとは関係ないが，このあたりで，ファイルの拡張子が表示されるようにしておくこと。（エクスプローラの表示タブ→「ファイル名拡張子」を有効にする。）
