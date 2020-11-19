# PM実験でやること（技術編）

## 準備

1. [GitHub](https://github.com/)のアカウントを作る（Sign up）．登録したメールアドレスにメールが来たら，「Varify email address」をクリックする．
1. 矢吹またはTAに作ったアカウントを報告し，チームのリポジトリ（ファイル置き場）への書き込み権限をもらう．
1. 各自にGitHubから権限付与を確認するメールが届く．このメールに対応すると，リポジトリに書き込めるようになる．**このメールの有効期限は短いことに注意．**
1. [この後の作業（解説動画）](https://youtu.be/1WSovwUgpFw)

注意：GitHubのページでは，機械翻訳はオフにしておいた方がよさそう．

## ウェブページの作成

1. [Visual Studio Codeの導入](vscode.md)
1. [ウェブページを書く練習](html.md)
1. [正しいHTML文書にする](validation.md)

## ウェブページの公開

前提：VS Codeをインストールしたときに，Gitもインストールしていること．（VS Codeでうまく行かない人は，[GitHub Desktop](https://desktop.github.com/)を試してみるとよい．操作方法は異なるが，必要なのが，①ステージ，②コミット，③プッシュであることに変わりはない．）

各チームのGitHubリポジトリにファイルを登録する．Visual Studio Codeで実行する方法については，[VS CodeでGitHubを使う](git.md)を参照．

**概要：公開するファイルを，フォルダhtdocsの中に保存する．トップページはindex.htmlである．**

1. 作業用のフォルダを作る．（例：c:/work）
1. エクスプローラでそのフォルダを開き，アドレス欄に「`powershell`」と入力する．（コマンド入力用のウィンドウが現れる．PowerShellを起動して，「`c:`」エンター，「`cd /work`」エンターでもよい．）
1. 「`git clone https://github.com/yabukilab/{チーム名}.git`」を実行する．`{チーム名}`の部分は，矢吹研Aなら`yabuki-a`．（フォルダができる．例：yabuki-a．このフォルダを右クリック→「Codeで開く」）
1. 上でできたフォルダの中に，htdocsというフォルダがある．公開するファイルはすべてその中に格納する．（このフォルダの中に格納したファイルしか公開できない．）
1. トップページはindex.htmlである．これは特別なファイルで，ファイル名を指定せずにアクセスできる．（例：http://yabukia.pm-chiba.tech/ にアクセスすると，リポジトリhttps://github.com/yabukilab/yabuki-a のhtdocs/index.htmlを閲覧することになる．）
1. 変更したファイルをステージ，コミット，プッシュする．
1. ウェブサイトを確認する．

## 重要なURL

### 各チームのリポジトリ

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

### 各チームのウェブサイト

HTMLやCSSに構文エラーがなければ「passing（緑色）」になる（プッシュしてしばらくすると更新される）．
構文エラーがあると「failing（赤）」になる．
構文エラーは「failing（赤）」のアイコンをクリックして確認することもできるが，見づらいため，[「正しいHTML文書」](validation.md)の方法でチェックすることを勧める．

チーム|URL|エラーチェックの結果
-|-|-
下田A|https://shimoda-a.pm-chiba.tech/|[![Build Status](https://travis-ci.com/yabukilab/shimoda-a.svg?branch=master)](https://travis-ci.com/github/yabukilab/shimoda-a)
下田B|https://shimoda-b.pm-chiba.tech/|[![Build Status](https://travis-ci.com/yabukilab/shimoda-b.svg?branch=master)](https://travis-ci.com/github/yabukilab/shimoda-b)
下田C|https://shimoda-c.pm-chiba.tech/|[![Build Status](https://travis-ci.com/yabukilab/shimoda-c.svg?branch=master)](https://travis-ci.com/github/yabukilab/shimoda-c)
小笠原A|https://ogasawara-a.pm-chiba.tech/|[![Build Status](https://travis-ci.com/yabukilab/ogasawara-a.svg?branch=master)](https://travis-ci.com/github/yabukilab/ogasawara-a)
小笠原B|https://ogasawara-b.pm-chiba.tech/|[![Build Status](https://travis-ci.com/yabukilab/ogasawara-b.svg?branch=master)](https://travis-ci.com/github/yabukilab/ogasawara-b)
小笠原C|https://ogasawara-c.pm-chiba.tech/|[![Build Status](https://travis-ci.com/yabukilab/ogasawara-c.svg?branch=master)](https://travis-ci.com/github/yabukilab/ogasawara-c)
矢吹A|https://yabuki-a.pm-chiba.tech/|[![Build Status](https://travis-ci.com/yabukilab/yabuki-a.svg?branch=master)](https://travis-ci.com/github/yabukilab/yabuki-a)
矢吹B|https://yabuki-b.pm-chiba.tech/|[![Build Status](https://travis-ci.com/yabukilab/yabuki-b.svg?branch=master)](https://travis-ci.com/github/yabukilab/yabuki-b)
矢吹C|https://yabuki-c.pm-chiba.tech/|[![Build Status](https://travis-ci.com/yabukilab/yabuki-c.svg?branch=master)](https://travis-ci.com/github/yabukilab/yabuki-c)
矢吹X|https://yabuki-x.pm-chiba.tech/|[![Build Status](https://travis-ci.com/yabukilab/yabuki-x.svg?branch=master)](https://travis-ci.com/github/yabukilab/yabuki-x)
田隈A|https://takuma-a.pm-chiba.tech/|[![Build Status](https://travis-ci.com/yabukilab/takuma-a.svg?branch=master)](https://travis-ci.com/github/yabukilab/takuma-a)
田隈B|https://takuma-b.pm-chiba.tech/|[![Build Status](https://travis-ci.com/yabukilab/takuma-b.svg?branch=master)](https://travis-ci.com/github/yabukilab/takuma-b)
田隈C|https://takuma-c.pm-chiba.tech/|[![Build Status](https://travis-ci.com/yabukilab/takuma-c.svg?branch=master)](https://travis-ci.com/github/yabukilab/takuma-c)

## 参考書

- 大藤幹ほか『HTML+CSSデザイン 基本原則、これだけ．』（MdN, 2013）（各研究室にある．熟読はしなくていいが，全ページをめくってみることを勧める．たとえば，「PCでもスマホでも快適に読めるようにするための技術」が**ある**ことは知っておくといい．具体的にどうするかは，必要になったときに勉強する．）

