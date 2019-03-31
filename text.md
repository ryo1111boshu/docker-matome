## コンテナとは
ホストOS上に論理的な区画（コンテナ）を作り、アプリケーションを動作させるのに必要なライブラリやアプリケーションなどを1つにまとめ、あたかも個別のサーバーのように使うことができるようにしたもの。

## ホストOS
ホストOSとは、仮想マシン（仮想コンピュータ）環境で仮想的なOSを動作させている（土台となっている）OSのことである。

## ステージング環境
継続的デリバリーが行われるシステム開発において、開発したアプリケーションをプロダクション環境にデプロイする直前に確認する、テスト環境のこと

## 継続的デリバリー（CD）
- CDとは、Continuous Deliveryの略で、継続的デリバリーと呼ばれています。
- 継続的デリバリー(CD)は、継続的インテグレーション(CI)を拡張した手法で、ビルドやテストだけでなく、リリースプロセス全体を自動化します。
- 実施の目的はDevOpsと同様で、リリーススピードを上げることで、素早く市場からフィードバックを得られ、ソフトウェアに反映させることができます。
- 継続的デリバリー(CD)では、すべてのコード変更は、ビルドとテストを実行した後、テスト環境またはステージング環境にデプロイして、システムテストやUIテストを行います。
- 開発者は、準備ができた時点で、最後のステップとして運用環境への更新を承認します。
- この点は、運用環境へのデプロイが明示的な承認なしで自動的に行われる「継続的デプロイ」とは異なります。

<img src="https://cloudbees.techmatrix.jp/wp-content/uploads/2018/03/cd_2.png">[引用元：https://cloudbees.techmatrix.jp/devops/cd/]

## イメージとは
Rubyでいうクラスみたいなもの？イメージをもとにコンテナ（インスタンス？）を稼働させる

## docker container runコマンドで、Dockerコンテナを作成/実行する
`docker container run [Dockerイメージ名] [実行コマンド]`
- 例：`docker container run ubuntu:latest /bin/echo 'Hello world'`

## docker versionコマンドを利用して、バージョンを確認する
`docker version`

## Docker hubからNginxの公式イメージをダウンロードして、Webサーバーを動かす
`docker pull nginx`

## docker image pullコマンドを利用して、Docker hubからイメージをダウンロードする
`docker image pull [オプション] イメージ名[:タグ名]`
- タグ名を省略すると最新版を取得する
- 以下の例はcentOSのバージョン7(タグ名：7)をダウンロードするコマンド
`docker image pull centos:7`

## docker image lsコマンドを利用して、取得したイメージの一覧表示をする
`docker image ls [オプション名] [レポジトリ名]`

## docker image inspectコマンドを利用して、イメージの詳細情報を確認する
`docker image inspect [イメージ名]`

## docker image rmコマンドを利用して、イメージを削除する
`docker image rm [オプション] [イメージ名]`
- 例: `docker image rm nginx`

## docker loginコマンドを利用して、Dockerhubにログイン
`docker login [オプション] [サーバー]`

## docker image pushコマンドを利用して、イメージをアップロード
`docker image push イメージ名[:タグ名]`
- イメージ名は次のようにする `<Docker Hub ユーザー名>/ イメージ名:[タグ名]`

## `docker container stats`コマンドを利用して、コンテナの稼働状況を確認する
`docker container stats [コンテナ名]`

## `docker container rm`コマンドを利用して、コンテナを削除する
`docker container rm [オプション] コンテナ識別子`

## `docker container pause/unpause`コマンドw利用して、コンテナの中断や再開をする
`docker container pause コンテナ識別子`

## Dockerネットワークとは
- Dockerコンテナ同士が通信するときに用いるネットワーク

## docker network lsコマンドを利用して、ネットワーク情報を表示させる
`docker network ls [オプション名]`

## `docker network create`コマンドを利用して、新しいネットワークを作成する
`docker network create [オプション] ネットワーク名`

## `docker network connect/disconnect`コマンドを利用して、DockerコンテナをDockerネットワークに接続する
`docker network connect [オプション] ネットワーク コンテナ`

## docker network inspectコマンドでネットワークの詳細を確認
`docker network inspect [オプション] ネットワーク`

## docker network rmコマンドでネットワークを削除
`docker network rm [オプション] ネットワーク`

## docker container attachコマンドで、稼働しているコンテナに接続

## docker container execコマンドで、稼働コンテナでプロセスを実行
`docker container exec [オプション] コンテナ識別子 実行するコマンド [引数]`

## docker container topコマンドで、稼働コンテナで実行されているプロセスを確認

## docker container renameコマンドを利用して、コマンドの名前を変更する
`docker container rename 元の名前　新しい名前`

## ホストとは
サービスを提供する側のコンピューターのこと。サーバーと似た意味で使われることがある。

## docker container cpコマンドで、コンテナ内のファイルをホストにコピー
`docker container cp コンテナ識別子:コンテナ内のファイルパス　ホストのディレクトリパス`

## docker container commitコマンドで、コンテナからイメージを作成
`docker container commit [オプション] コンテナ識別子　[イメージ名：タグ名]`

## Dockerfileとは
- インフラ構成を記述したファイル

## docker buildコマンドを利用して、Dockerfileの情報からイメージを作成する
`docker build -t [生成するイメージ名]:[タグ名] [Dockerfileの場所]`
