# VS CodeでGitHubを使う

前提：[Git](https://git-scm.com/downloads)がインストールされている。

## 初期設定

`Ctrl+@`でターミナルを開き，以下を実行する。

1. `git config --global user.name "{ユーザ名}"`を実行する。（`{ユーザ名}`の部分は適当な名前（GitHubのユーザ名など）で置き換える。）
1. `git config --global user.email {メアド}`を実行する。（`{メアド}`の部分は適当なメアド（GitHubに登録したメアド）で置き換える。）
1. `git clone リポジトリのURL`を実行する。（例：`git clone https://github.com/yabukilab/yabuki-a.git`）

## 開発時

基本的な操作（ステージング・コミット・プッシュ）は以下のように行う。

1. `Ctrl+Shift+E`でエクスプローラタブを開き，リポジトリのフォルダで新しいファイルやフォルダを作る。
1. ファイルを編集する。
1. （作業が一段落したら）`Ctrl+Shift+G`でソース管理タブを開き，バージョン管理するファイルの「+」アイコンを押して**ステージング**する。
1. メッセージを入力して，`Ctrl+Enter`（**コミット**）
1. 「･･･」をクリックし，プルダウンメニューの「**プッシュ**」をクリックする。**（初めての時は，GitHubのユーザ名とパスワードを訊かれる。）**
1. GitHubのウェブサイト（例：https://github.com/yabukilab/yabuki-a ）で，ファイルが更新されていることを確認する。
1. **PM実験・演習**公開用のウェブサイト（例：http://yabukia.pm-chiba.tech/ ）が更新されていることを確認する。