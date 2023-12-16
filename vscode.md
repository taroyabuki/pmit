# VSCode（Visual Studio Code）の導入

## インストール

VSCodeをインストールする．[ウェブサイト](https://code.visualstudio.com)からダウンロードしてもよいし，PowerShellで`winget install Microsoft.VisualStudioCode`としてもよい．

## VSCodeの拡張機能

VSCodeを起動し、`Ctrl+Shift+x`で拡張機能の検索タブを開き，キーワードを入れると該当する拡張機能が出てくる．名前を確認して、「Install」（または「インストール」）をクリックしてインストールする．

名前|キーワード|メモ
---|---|---
Hex Editor|`hex`|ファイルのダンプ（バイト列の表示）
Live Preview|`live preview`|HTMLのプレビュー（右上のプレビューボタン）．HTMLファイルをブラウザで開くより簡単．
W3C Web Validator|`w3c`|HTMLの構文の検証
Japanese Language Pack for Visual Studio Code|`japanese`|日本語UI

## VSCodeのその他の設定

Ctrl+,（あるいはファイル→ユーザ設定→設定）で設定タブを開いて設定する．

- 保存時にHTMLの構文を検証する：`webvalidator.validateOnSave`を検索し，有効にする．
- （オプション）HTMLファイルの保存時にプレビューを自動更新する：`livePreview.autoRefreshPreview`を検索し，設定を`On Changes to Saved Files`にする．（機能しない場合は元に戻す．）
- （オプション）空白文字を見やすくする：`whitespace`を検索し，Editor: Render Whitespaceを「all」にする．

## 補足：ブラウザ上のVSCode

自分のPCにVSCodeをインストールしなくても，GitHub上のファイルは，ブラウザ上のVSCodeで編集できる．
Live PreviewやW3C Web Validationは動かないようだが，簡単なファイル編集ならこれで十分かもしれない．
次のいずれかで使えるようになる．

- GitHub上でキーボードの「.」（ドット）をクリックする．
- URLの`github.com`を`github.dev`に変える．
