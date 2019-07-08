# CITools

## 本ドキュメントの目的
構成、サーバー構築、起動手順を示す。


## 概要
コードの静解析（複雑度、脆弱性、バグ誘発コード検知等）、<br/>
動解析（UT、カバレッジ計測）を自動的に行い、<br/>
アプリケーションの品質を継続的に見える化するツール群です。

## 構成
〇ミドルウェア
* CI : Jenkins 2.150.1
* コード品質解析ツール：SonarQube 6.7.6

〇仮想サーバー環境
* OS : Ubuntu 16.04 LTS


## 前提条件

* gitがインストール済みであること。
* Virtualbox最新版がインストール済みであること
* Vagrant最新版がインストール済みであること


## サーバー構築手順
１. 作業用ディレクトリの作成：

　コマンドプロンプトを起動し、適当な場所に作業用ディレクトリを作成し、<br/>
作成したディレクトリ下に移動する。（以下、D:\WorkSpaceとする）
 

 `$ mkdir WorkSpace`
 
 `$ cd WorkSpace`

２．ソースコード取得：
以下のコマンド実行する。

`$ git clone git@github.com:JojiKoike/CITools.git`

３．サーバー構築（その１）：基本セットアップ

以下のコマンドを実行する。

 `$ vagrant up`


※この時点では、Jenkinsのアクティベーションが未完の為<br/>
　プラグインのインストールタスクに失敗する。<br/>
  現時点では自動化対応が難しいので、次の手順にて手動で行う。


４．サーバー構築（その２）：Jenkinsのアクティベーション

後日追記します。

５．サーバー構築（その３）：Jenkinsアクティベーション要タスクの完了

以下のコマンドを実行する。

`$ vagrant reload --provision`


※この時点で、Jenkinsの追加プラグインインストールが完了する。<br/>


６．SonarQube初期設定

作成中


７．SonarQubeプロジェクト作成

作成中

８．Jenkins-SonarQube連携設定

作成中


## 仮想サーバー環境使用方法
以下、コマンドプロンプトにて実行

1. 起動 : `$ vagrant up`

2. 停止 : `$ vagrant halt`

3. 再起動 : `$ vagrant reload`

## 各ツールログインアカウント
〇 Jankins
 * URL : http://localhost:8081
 * ID : jenkinsadmin
 * PWD : admin

〇 SonarQube
 * URL : http://localhost:8082
 * ID  : admin
 * PWD : admin


## 作者

 Joji KOIKE


## ライセンス（例）

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
