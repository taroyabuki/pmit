# ウェブアプリの開発環境（Docker）

ウェブサーバApache，データベース管理システムMySQL（MariaDB），管理インタフェースphpMyAdminを，一つのコンテナで実現する方法を紹介する。♠別々のコンテナで実現する方が実用的かもしれない（[compose](compose)を参照）。

メリット

- 全員の開発環境が同じになる。
- よくわからなくなったときに，全部消してやり直すのが簡単（コンテナを削除するだけ）。

デメリット

- 慣れないうちは，「コンテナの中での作業」というのがわかりにくい。

## 前提

- Dockerの動作確認はできている（[/docker](/docker)を参照）。
- VS Codeに次の拡張機能が入っている。
    - Dev Containers
    - Japanese Language Pack for Visual Studio Code（必須ではないが，ここでの説明はこれを前提にする。）
- **作業フォルダ**を適当に決める。空のフォルダがよい（例：c:/workを新規作成）。

エクスプローラで作業フォルダを開いた状態で，アドレスバーに`bash`と入力してターミナルを起動して作業する。

## コンテナの構築

```bash
docker run --rm -d -p 80:80 -v "$(pwd):/var/www" --name lamp taroyabuki/pm-lamp
```

> [!CAUTION]
> 説明しやすくするために，`lamp`という名前を付けている。同じ名前のコンテナをもう一つ作ろうとするとエラーになる。その場合は，後述の方法で一度コンテナを削除する。

動作確認：http://localhost/phpmyadmin/ にアクセスして，ユーザ名`testuser`，パスワード`pass`でログインできることを確認する。

> [!TIP]
> やり直したいときは，次のようにしてコンテナを削除する。

```
docker rm -f lamp
```

## コンテナ内での作業

1. VS Codeの左下のアイコンをクリック→「実行中のコンテナーにアタッチ...」でコンテナlampに接続する。♠慣れているなら`docker exec -it bash lamp`でもよい。
1. ファイル→「フォルダーを開く」で`/var/www`を開く。
1. Ctrl+Shift+@でターミナルを開く。

> [!TIP]
> このフォルダは，作業フォルダ（`docker run`を実行したフォルダ）と同じにしてある。`-v "$(pwd):/var/www"`がそssのためのオプションである。

## リポジトリのクローン

ターミナルで次を実行すると，/var/wwwにリポジトリがクローンされる（**`yabuki-x`の部分は自分のチームの名前で置き換える**）。

```bash
cd /var/www
git clone https://github.com/yabukilab/yabuki-x.git
```

ドキュメントルート（公開するフォルダの基点）を設定する。

```bash
rm -rf html
ln -s yabuki-x/htdocs html
```

> [!TIP]
> 次のフォルダは同じものである（`yabuki-x`の部分は自分のチームの名前で置き換える）。

- ホストの，作業フォルダ/html
- ホストの，作業フォルダ/yabuki-x/htdocs
- コンテナの，/var/www/html
- コンテナの，/var/www/yabuki-x/htdocs

> [!TIP]
> ここでの作業の結果はホスト側に残るため，コンテナを再構築した場合に繰り返す必要はない。

## ウェブページの作成

a.htmlというファイルを作って閲覧してみよう。

VS Codeで/var/www/html/a.htmlを作る。内容は適当でよい。♠コンソールで`echo hello > /var/www/html/a.html`などとしてもよい。

http://localhost/a.html でページが表示されることを各委任する。

## バージョン管理

### 準備

VS Codeにリポジトリを認識させる。

1. VS Codeで，フォルダ/var/www/yabuki-xを開く（`yabuki-x`の部分は自分のチームの名前で置き換える）。
1. 左側の枝分かれの絵のアイコンをクリック，「Manage unsafe repository」をクリックして，/var/www/yabuki-xを指定する。

### a.htmlの管理

上で作成したa.htmlをリポジトリに追加する。

1. （プル）
1. ステージ
1. コミット
1. プッシュ

（オプション）GitHubに変更がある場合は，先に**プル**しておく（`yabuki-x`の部分は自分のチームの名前で置き換える）。

```bash
cd /var/www/yabuki-x
git pull
```

a.htmlをバージョン管理の対象にする（**ステージ**）。

```bash
cd /var/www/html
git add a.html
```

変更を確定する**コミット**。コミットメッセージは丁寧に書いておくとよい。

```bash
git commit -m "test page"
```

ここまでがローカルでのバージョン管理。最後に，GtHubに**プッシュ**するのだが，認証の手間を少し減らすために，VS CodeのGUIの「変更の同期」を使う。

> [!TIP]
> プッシュだけでなく，プル，ステージ，コミットもVS Code上で行える。

> [!TIP]
> よくわからなくなったら，次のようにローカルのリポジトリを削除して，上の「クローン」からやり直す。参照：https://naglly.com/archives/2015/10/xkcd-git.php

```bash
rm -rf /var/www/yabuki-x
```

## 公開

GitHubに登録すれば，あとは自動で公開されるはず。

結果の確認：https://yabuki-x.pm-chiba.tech/a.html でページが表示されることを確認する（`yabuki-x`の部分は自分のチームの名前で置き換える）。

ちなみに，ローカルでの確認はhttp://localhost/a.html だった。

## データベースを使うウェブアプリ

https://github.com/taroyabuki/pmpractice2 の「詳しい説明」のところを順番にやっていけばよいのだが，動作確認のために，[全データ表示（実装）](https://github.com/taroyabuki/pmpractice2/tree/master/patterns/show-all)を再現する。

1. ターミナルで`mysql`として，MySQL（MariaDB）に接続する（終了はCtrl-d）。
2. データベースを作る。

```sql
create database mydb charset=utf8mb4;
```

3. テーブルを作る。

```sql
use mydb;

create table table1 (
  id int primary key auto_increment, # ここはいつも同じ
  varcharA varchar(40) not null,
  intA int not null,
  intB int not null # 最後にはカンマがないことに注意．
);
```

4. データを入力する。

```sql
insert into table1 (id, varcharA, intA, intB) values
(1, 'A', 1280, 1),
(2, 'B', 2980, 0),
(3, 'C', 198, 121);
```

5. /var/www/html/db.php を作る（[内容](https://github.com/taroyabuki/pmpractice2/blob/master/db.php)）。
6. /var/www/html/show-all.php を作る（[内容](https://github.com/taroyabuki/pmpractice2/blob/master/patterns/show-all/show-all1.php)）
7. 動作確認：http://localhost/show-all.php

## 練習

### 練習1

（コンテナの中ではなく）ホストで`docker rm -f lamp`としてコンテナを削除して，最初からやり直してみる。

### 練習2

コンテナを削除して，http://localhost/show-all.php を再現する。ただし今回は，コードはAIに書かせる。プロンプトを書く練習である。

## 次に学ぶこと

https://github.com/taroyabuki/pmpractice2 の「詳しい説明」のところを順番にやってみよう。

## ♠参考：イメージの作り方（環境構築法）

> [!NOTE]
> 以下は参考資料である。興味が無い者は読まなくてよい。

次のような手順で必要なソフトウェアをインストールする。

```bashss
# コンテナ構築
docker run --rm -d -p 80:80 ubuntu:24.04
``` 

後はコンテナ内での作業（プロンプトは`#`）。

```bash
# ウェブサーバとデータベース管理システムのインストール
apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends git apache2 libapache2-mod-php php-mbstring mariadb-server mariadb-client debconf-utils

# 警告回避
echo 'ServerName localhost' >> /etc/apache2/apache2.conf

# ウェブサーバ起動
apachectl start
```

動作確認 http://localhost

```bash
# データベースサーバ起動
service mariadb start

# データベースのユーザ作成
mysql << EOF
CREATE USER 'testuser'@'localhost' IDENTIFIED BY 'pass';
GRANT ALL PRIVILEGES ON *.* TO 'testuser'@'localhost';
FLUSH PRIVILEGES;
EOF

# データベース管理アプリphpMyAdminのインストール
# apt-get install -y --no-install-recommends phpmyadmin
# 質問に，次のように答えるのを自動化する。
#Configure database for phpmyadmin with dbconfig-common? [yes/no] yes
#
#MySQL application password for phpmyadmin: 入力せずにEnter
#
#Web server to reconfigure automatically: 1

debconf-set-selections <<EOF
phpmyadmin phpmyadmin/dbconfig-install boolean true
phpmyadmin phpmyadmin/app-password-confirm password 
phpmyadmin phpmyadmin/mysql/admin-pass password 
phpmyadmin phpmyadmin/mysql/app-pass password 
phpmyadmin phpmyadmin/reconfigure-webserver multiselect apache2
EOF

apt-get install -y --no-install-recommends phpmyadmin

# ウェブサーバ再起動
apachectl restart
```

動作確認（ユーザ名testuser，パスワードpass） http://localhost/phpmyadmin

以上の全体を[Dockerfile](Dockerfile)にまとめて，そのファイルがあるフォルダで`docker build -t pm-lamp .`として，イメージを構築した。
