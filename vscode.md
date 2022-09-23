# VSCode（Visual Studio Code）の導入

## インストール

VSCodeをインストールする．[ウェブサイト](https://code.visualstudio.com)からダウンロードしてもよいし，PowerShellで`winget install Microsoft.VisualStudioCode`としてもよい．

## VSCodeの拡張機能

VSCodeを起動し、`Ctrl+Shift+x`で拡張機能の検索タブを開き，キーワードを入れると該当する拡張機能が出てくる．名前を確認して、「Install」（または「インストール」）をクリックしてインストールする．

名前|キーワード|メモ（使用する講義等）
---|---|---
hexdump for VSCode|`hexdump`|講義「情報リテラシ」
W3C Web Validation|`w3c`|講義「情報リテラシ」，PM実験，PM演習
Japanese Language Pack for Visual Studio Code|`japanese`|日本語UIが不要なら入れなくてもよい．

## VSCodeのその他の設定

- 空白文字を見やすくするために，`Ctrl+,(Comma)`で設定タブを開き，検索欄に`whitespace`と入力，Editor: Render Whitespaceを「all」にする．

補足：自分のPCにVSCodeをインストールしなくても，次のいずれかの方法で，ブラウザ上でVSCodeが使える．
W3C Web Validationは動かないようだが，簡単なファイル編集ならこれで十分かもしれない．

- GitHub上でキーボードの「.」（ドット）をクリックする．
- URLの`github.com`を`github.dev`に変える．

VSCodeとは関係ないが，このあたりで，ファイルの拡張子が表示されるようにしておくこと．（エクスプローラの表示タブ→「ファイル名拡張子」を有効にする．）
