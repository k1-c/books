# Docker/Kubernetes 実践コンテナ開発入門

## 目次

1. Dockerの基礎
    1. Dockerとは
        - Dockerの歴史
        - Dockerの基礎概念
        - Dockerの考えに触れる
    2. Dockerを利用する意義
        - 環境差異問題からの脱却
        - アプリケーションの構成管理のしやすさ
        - 本番環境に導入してこそのDocker
        - 新しい開発スタイルへ
    3. ローカルDocker環境を構築する
        - Docker for Windowsのインストール
        - Docker for Macのインストール
        - Docker for Windows/Macの基本設定
2. Dockerコンテナのデプロイ
    1. コンテナでアプリケーションを実行する
        - DockerイメージとDockerコンテナの基本
        - 簡単なアプリケーションとDockerイメージをつくる
        - Dockerコンテナを実行する
    2. Dockerイメージの操作
        - docker image build - イメージのビルド
        - docker search - イメージの検索
        - docker image pull - イメージの取得
        - docker image ls - イメージの閲覧
        - docker image tag - イメージのタグ付け
        - docker image push - イメージの公開
    3. Dockerコンテナの操作
        - Dockerコンテナのライフサイクル
        - docker container run - コンテナの作成と実行
        - docker container ls - コンテナの一覧
        - docker container stop - コンテナの停止
        - docker container restart - コンテナの再起動
        - docker container rm - コンテナの破棄
        - docker container logs - 標準出力での取得
        - docker container exec - 実行中コンテナでのコマンド実行
        - docker container cp - ファイルのコピー
    4. 運用管理向けコマンド
        - prune - 破棄
        - docker container stats - 利用状況の取得
    5. Docker Composeでマルチコンテナを実行する
        - docker composeによるコンテナの実行
    6. Composeによる複数コンテナの実行
3. 実用的なコンテナの構築とデプロイ
    1. アプリケーションとコンテナの粒度
        - 1コンテナ=1プロセス？
        - 1コンテナに1つの関心事
    2. コンテナのポータビリティ
        - Kernel・アーキテクチャの違い
        - ライブラリ・ダイナミックリンクの課題
    3. Dockerフレンドリなアプリケーション
        - 環境変数を活用する
    4. 永続化データをどう扱うか
        - Data Volume
        - Data Volumeコンテナ
    5. コンテナ配置戦略
        - Docker Swarm
        - Service
        - Stack
        - ServiceをSwarmクラスタ外から利用する
4. Swarmによる実践的なアプリケーション構築
    1. Webアプリケーションの構成
        - アプリケーションの仕様
        - アーキテクチャ
        - TODOアプリケーション構築の全体像
    2. MySQL Serviceの構築
        - データベース・コンテナ構成
        - 認証情報
        - MySQLの設定 - etc/mysql/mysql.conf.d/mysqld.cnf
        - レプリケーションを設定する
        - MySQL（mysql_master/mysql_slave）のDockerファイル
        - Swarm上でMaster/Slaveサービスを実行する
        - MySQLコンテナを確認し、初期データを投入する
    3. API Serviceの構築
        - todoapiの基本構造
        - アプリケーションでの環境変数の制御
        - MySQL接続、テーブルマッピング
        - Handlerを実装する
        - APIのDockerfile
        - Swarm上でtodoapiサービスを実行する
    4. Nginxの構築
        - nginx.confを構築する
        - NginxのDockerfile
        - Nginxを通してアクセスできるようにする
    5. Webの構築
        - TODO APIを呼び出し、ページのHTMLを返却する
        - WebのDockerfile
        - 静的ファイルの扱いを工夫する
        - Nginxを通してアクセスできるようにする
        - Ingressで公開する
    6. コンテナオーケストレーションによる開発スタイル
5. Kubernates入門
    1. Kubernetesとは
        - Dockerの隆盛とKubernetesの誕生
        - Kubernetesの位置付け
    2. ローカル環境でKubernetesを実行する
        - Docker for Windows/MacでローカルKubernates環境を構築する
    3. Kubernetesの概念
    4. KubernetesクラスタとNode
    5. Namespace
    6. Pod
        - Podを作成してデプロイする
        - Podを操作する
    7. ReplicaSet
    8. Deployment
        - ReplicaSetライフサイクル
        - ロールバックを実行する
    9. Service
        - ClusterIP Service
        - NodePort Service
        - LoadBalancer Service
        - ExternalName Service
    10. Ingress
        - Ingressを通じたアクセス
6. Kubernetesのデプロイ・クラスタ構築
    1. Google Kubernetes Engineのセットアップ
        - GCPプロジェクトの作成
        - Google Clocd SDK（gcloud）のセットアップ
        - Kubernetesクラスタの作成
    2. GKE上にTODOアプリケーションを構築する
    3. Master Slave構成のMySQLをGKE上に構築する
        - PersistentVolumeとPersistentVolumeClaim
        - StorageClass
        - StatefulSet
    4. TODO APIをGKE上に構築する
    5. TODO WebアプリケーションをGKE上に構築する
    6. IngressでWebアプリケーションをインターネットに公開する
    7. オンプレミス環境でのKubernetesクラスタの構築
    8. kubesprayでKubernetesクラスタを構築する
        - クラスタとして構築するサーバの準備
        - opsのSSH公開鍵の登録
        - IPv4フォワーディングを有効にする
        - クラスタの設定
        - クラスタ構築の実行
7. Kubernetesの発展的な利用
    1. Kubernetesの様々なリソース
        - Job
        - CronJob
        - Secret
    2. ユーザー管理とRole-Based Access Control（RBAC）
        - RBACを利用して権限制御を実現する
        - ServiceAccount
    3. Helm
        - Helmのセットアップ
        - Helmの概念
        - Chartをインストールする
        - Chartでアプリケーションをアンインストールする
        - RBACに対応したアプリケーションをインストールする
        - 独自のChartを作成する
    4. Kubernatesにおけるデプロイ戦略
        - RollingUpdate
        - コンテナ実行時のヘルスチェックを設定する
        - BlueGreen Deployment
8. コンテナの運用
    1. ロギングの運用
        - コンテナにおけるロギング
        - コンテナログの運用
        - FluentdとElasticsearchによるログ収集・検索機構の構築
        - fluentd logging driverの運用イメージ
        - Kubernatesにおけるログの管理
        - その他のログ収集ツール
    2. Dockerホストやデーモンの運用
        - コンテナのライブリストア
        - dockerdのチューニング
    3. 障害対策
        - Docker運用での障害対策
        - Kubernates運用での障害対策
9. より軽量なDockerイメージを作る
    1. なぜ軽量なイメージを作るべきなのか
        - イメージサイズの増大で発生する弊害
    2. 軽量なベースイメージ
        - scratch
        - BusyBox
        - Alpine Linux
    3. 軽量なDockerイメージをつくる
    4. multi-stage builds
        - ビルドコンテナと実行コンテナを分ける
10. Dockerの様々な活用方法
    1. チーム開発で開発環境を統一・共有する
        - 利用するソフトウェア・ツールを統一する
        - 開発環境は集合知
    2. コマンドラインツールをDockerコンテナで利用する
        - イメージによって利用するCLIのバージョンを切り替える
        - シェルスクリプトをDockerコンテナで実行する
    3. 負荷テスト
        - 実験環境のセットアップ
        - master/slave構成で複数コンテナから負荷テストを実行する
        

