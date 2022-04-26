# Docker

Dockerの概要は『ゼロからはじめるデータサイエンス入門』（講談社, 2021）などを参照．

## 準備

1. Windows updateでWindowsを最新状態にする．
1. WSL2のインストール

スタートメニューを右クリック→Windows PowerShell（管理者）で次を実行する．（初回起動時にユーザ名とパスワードを設定する．パスワードは画面に表示されない．）

```bash
wsl --install -d Ubuntu
```

3. Dockerのインストール

PowerShellで次を実行する．（`winget`を実行できない場合は，Microsoft Storeで「アプリ インストーラー」をインストールする．

```bash
winget install Docker.DockerDesktop
```

コンピュータを一度再起動して，Docker Desktopを起動してみる．エラーメッセージが表示されたら，その指示に従う．

## 動作確認

1. Dockerの動作確認

PowerShellで次を実行する．

```bash
docker run --rm hello-world
```

次のようなメッセージが表示されればよい．

```
Hello from Docker!
This message shows that your installation appears to be working correctly.

（以下略）
```

2. ネットワークの動作確認

PowerShellで次を実行する．

```bash
docker run -it --rm busybox nslookup -type=a www.google.com
```

次のようなメッセージが表示されればよい（完全に同じで無くてもよい）．

```
Server:         192.168.65.5
Address:        192.168.65.5:53

Non-authoritative answer:
Name:   www.google.com
Address: 216.58.220.100
```

うまく行かない場合は，画面右下のDockerアイコンを右クリック→Settings→Resources→Networkを確認する．アクセスできないサーバがDNSとして設定されているとうまく行かない．
