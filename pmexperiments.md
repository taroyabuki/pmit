# PM実験でやること（技術編）

## 準備

1. GitHubのアカウントを持っていない場合：
    - https://github.com （**GitHub Educationではない**）の「Sign up」でアカウントを作る．
    - 登録には大学のメアド（s.chibakoudai.jp）を使う．
    - ☑メアドの確認のためのメールが届くから，それに対応する．
    - （オプション）https://github.com/settings/emails で別のメアドを登録しておくと，卒業後も使い続けられる．
1. チーム分けが終わったら，そのチームのGitHubリポジトリ（ファイル置き場）への招待メールが届く．
1. ☑メールに対応すると，リポジトリに書き込めるようになる．**このメールの有効期限は短い．** 有効期限が過ぎてしまった場合は矢吹に連絡する．

**注意：GitHubのページを丸ごと翻訳してはいけない．専門用語が翻訳されると，意味不明になる．（例：master→主人，raw→生）**

## ウェブページの作成

1. [VSCodeの導入](vscode.md)
1. [ウェブページを書く練習](html.md)
1. [正しいHTML文書にする](validation.md)

## ウェブページの公開

概要：公開するファイルを，フォルダ**htdocs**の中に保存する．トップページは**index.html**である．

できあがりの例：

- リポジトリ：https://github.com/yabukilab/yabuki-x
- ウェブサイト：https://yabuki-x.pm-chiba.tech

やり方：[VSCodeでGitHubを使う](git.md)

VSCodeでうまく行かない人は，[GitHub Desktop](https://desktop.github.com)を試してみるとよい．操作方法は異なるが，必要なのが，①ステージ，②コミット，③プッシュであることに変わりはない．

### 各チームのURL

リポジトリ|ウェブサイト
--|--
https://github.com/yabukilab/ogasawara-a/|https://shimoda-a.pm-chiba.tech
https://github.com/yabukilab/ogasawara-b/|https://shimoda-b.pm-chiba.tech
https://github.com/yabukilab/ogasawara-c/|https://shimoda-c.pm-chiba.tech
https://github.com/yabukilab/ogasawara-d/|https://shimoda-d.pm-chiba.tech
https://github.com/yabukilab/shimoda-a/|https://ogasawara-a.pm-chiba.tech
https://github.com/yabukilab/shimoda-b/|https://ogasawara-b.pm-chiba.tech
https://github.com/yabukilab/shimoda-c/|https://ogasawara-c.pm-chiba.tech
https://github.com/yabukilab/shimoda-d/|https://ogasawara-d.pm-chiba.tech
https://github.com/yabukilab/yabuki-a/|https://yabuki-a.pm-chiba.tech
https://github.com/yabukilab/yabuki-b/|https://yabuki-b.pm-chiba.tech
https://github.com/yabukilab/yabuki-c/|https://yabuki-c.pm-chiba.tech
https://github.com/yabukilab/yabuki-d/|https://yabuki-d.pm-chiba.tech
https://github.com/yabukilab/yabuki-x/|https://yabuki-x.pm-chiba.tech

### 構文チェックの結果

https://admin.pm-chiba.tech/report.php

HTMLやCSSに構文エラーがなければ![passing（緑色）](img/passing.svg)になる（プッシュしてしばらくすると更新される）．
構文エラーがあると![failing（赤）](img/failing.svg)になる．
エラーは![failing（赤）](img/failing.svg)をクリックして確認できる．
しかし，[「正しいHTML文書」](validation.md)の方法で，VSCode上でチェックすることを勧める．

## 参考書

- [大藤幹ほか『HTML+CSSデザイン 基本原則、これだけ．』（MdN, 2013）](https://calil.jp/book/4844363581)
- [エビスコム『HTML5&CSS3デザイン 現場の新標準ガイド 体系的に学ぶＨＴＭＬとＣＳＳの仕様と実践』（マイナビ, 第2版, 2020）](https://calil.jp/book/4839974594)
