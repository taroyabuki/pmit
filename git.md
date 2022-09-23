# VSCodeでGitHubを使う

## 準備

1. Gitをインストールする．[ウェブサイト](https://git-scm.com/downloads)からダウンロードしてもよいし，PowerShellで`winget install Git.Git`としてもよい．
1. VSCodeを起動し，`Ctrl+@`でターミナルを開き，以下を実行する．（**プロンプトを見て，作業フォルダがどこなのかを確認すること**）
    1. `git config --global user.name "ユーザ名"`を実行する．（`ユーザ名`の部分は適当な名前で置き換える．）
    1. `git config --global user.email メアド`を実行する．（`メアド`の部分は適当なメアドで置き換える．）
    1. `git config --global core.autocrlf false`を実行する．（改行コードの勝手な変換を抑止するため）
    1. `git clone リポジトリのURL`を実行する．（例：`git clone https://github.com/yabukilab/yabuki-x.git`）

## 基本的な作業

以下を繰り返す．

1. **ステージング**：新しく作ったり更新したファイルをバージョン管理することの宣言
1. **コミット**：自分のPC上でのファイルのバージョン管理
1. **プッシュ**：GitHub上でのバージョン管理

具体的な操作は次のとおり．

1. `Ctrl+Shift+E`でエクスプローラタブを開き，リポジトリのフォルダで新しいファイルやフォルダを作る．
1. ファイルを編集する．
1. （作業が一段落したら）`Ctrl+Shift+G`でソース管理タブを開き，バージョン管理するファイルの「+」アイコンを押して**ステージング**する．
1. メッセージを入力して「**コミット**」
1. 「･･･」をクリックし，プルダウンメニューの「**プッシュ**」をクリックする．**（初めての時は，GitHubのユーザ名とパスワードを訊かれる．）**
1. GitHubのウェブサイト（例：https://github.com/yabukilab/yabuki-x ）で，ファイルが更新されていることを確認する．
1. **PM実験・演習**公開用のウェブサイト（例：https://yabuki-x.pm-chiba.tech ）が更新されていることを確認する．
