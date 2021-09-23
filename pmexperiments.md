# PM実験でやること（技術編）

## 準備

1. チーム分けが終わったら，そのチームためのGitHubリポジトリ（ファイル置き場）への招待メールが届く．
1. メールに対応すると，リポジトリに書き込めるようになる．**このメールの有効期限は短いことに注意．**
1. [この後の作業（解説動画）](https://youtu.be/1WSovwUgpFw)

注意：GitHubのページでは，機械翻訳はオフにしておいた方がよさそう．

## ウェブページの作成

1. [VSCode（Visual Studio Code）の導入](vscode.md)
1. [ウェブページを書く練習](html.md)
1. [正しいHTML文書にする](validation.md)

## ウェブページの公開

前提：[VSCode](vscode.md)と[Git](git.md)がインストール済み．（ただし，VSCodeでうまく行かない人は，[GitHub Desktop](https://desktop.github.com/)を試してみるとよい．操作方法は異なるが，必要なのが，①ステージ，②コミット，③プッシュであることに変わりはない．）

各チームのGitHubリポジトリにファイルを登録する．Visual Studio Codeで実行する方法については，[VSCodeでGitHubを使う](git.md)を参照．

概要：公開するファイルを，フォルダ**htdocs**の中に保存する．トップページは**index.html**である．

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
構文エラーは「failing（赤）」のアイコンをクリックして確認することもできるが，少し時間がかかるため，[「正しいHTML文書」](validation.md)の方法でチェックすることを勧める．
ブラウザのキャッシュのせいでアイコンが変わらない場合がある．
おかしいと思ったら，Shiftを押しながら更新ボタンをクリックしてみよ．

チーム|URL|エラーチェックの結果
-|-|-
下田A|https://shimoda-a.pm-chiba.tech/|[![Build Status](https://admin.pm-chiba.tech/log/shimoda-a.svg)](https://admin.pm-chiba.tech/log/shimoda-a-validator.log)
下田B|https://shimoda-b.pm-chiba.tech/|[![Build Status](https://admin.pm-chiba.tech/log/shimoda-b.svg)](https://admin.pm-chiba.tech/log/shimoda-b-validator.log)
下田C|https://shimoda-c.pm-chiba.tech/|[![Build Status](https://admin.pm-chiba.tech/log/shimoda-c.svg)](https://admin.pm-chiba.tech/log/shimoda-c-validator.log)
小笠原A|https://ogasawara-a.pm-chiba.tech/|[![Build Status](https://admin.pm-chiba.tech/log/ogasawara-a.svg)](https://admin.pm-chiba.tech/log/ogasawara-a-validator.log)
小笠原B|https://ogasawara-b.pm-chiba.tech/|[![Build Status](https://admin.pm-chiba.tech/log/ogasawara-b.svg)](https://admin.pm-chiba.tech/log/ogasawara-b-validator.log)
小笠原C|https://ogasawara-c.pm-chiba.tech/|[![Build Status](https://admin.pm-chiba.tech/log/ogasawara-c.svg)](https://admin.pm-chiba.tech/log/ogasawara-c-validator.log)
矢吹A|https://yabuki-a.pm-chiba.tech/|[![Build Status](https://admin.pm-chiba.tech/log/yabuki-a.svg)](https://admin.pm-chiba.tech/log/yabuki-a-validator.log)
矢吹B|https://yabuki-b.pm-chiba.tech/|[![Build Status](https://admin.pm-chiba.tech/log/yabuki-b.svg)](https://admin.pm-chiba.tech/log/yabuki-b-validator.log)
矢吹C|https://yabuki-c.pm-chiba.tech/|[![Build Status](https://admin.pm-chiba.tech/log/yabuki-c.svg)](https://admin.pm-chiba.tech/log/yabuki-c-validator.log)
矢吹X|https://yabuki-x.pm-chiba.tech/|[![Build Status](https://admin.pm-chiba.tech/log/yabuki-x.svg)](https://admin.pm-chiba.tech/log/yabuki-x-validator.log)
田隈A|https://takuma-a.pm-chiba.tech/|[![Build Status](https://admin.pm-chiba.tech/log/takuma-a.svg)](https://admin.pm-chiba.tech/log/takuma-a-validator.log)
田隈B|https://takuma-b.pm-chiba.tech/|[![Build Status](https://admin.pm-chiba.tech/log/takuma-b.svg)](https://admin.pm-chiba.tech/log/takuma-b-validator.log)
田隈C|https://takuma-c.pm-chiba.tech/|[![Build Status](https://admin.pm-chiba.tech/log/takuma-c.svg)](https://admin.pm-chiba.tech/log/takuma-c-validator.log)

補足：自分でチェックする場合は次の通り．（Ubuntuの場合）

```bash
# 準備
sudo apt update
sudo apt install default-jre
pip3 install html5validator

# チェック
cd リポジトリのトップディレクトリ
html5validator --root htdocs/ --also-check-css
```

## 参考書

- 大藤幹ほか『HTML+CSSデザイン 基本原則、これだけ．』（MdN, 2013）（各研究室にある．熟読はしなくていいが，全ページをめくってみることを勧める．たとえば，「PCでもスマホでも快適に読めるようにするための技術」が**ある**ことは知っておくといい．具体的にどうするかは，必要になったときに勉強する．）
