# Webサービスを提供する企業の分析基盤

## ● Mercari
### ログの収集
- fluentd
- embulk
### ワークフローエンジン
- Digdag
### ログのストリーミング処理
- Norikra  
  SQLLikeにログデータを処理  
  fluentdのプラグイン経由でデータを吸い上げて集計することにより、無駄なデータ容量を削減できる
### ログの蓄積
- BigQuery
- Cloud Storage
- S3
### ビジュアライズ、BIツール
- Chartio  
  WebUIでダッシュボードを作成可能。  
  異なるサービスの複数データソースをINPUTとすることが可能
- Google Spread Sheet
- Kibana
### ビジュアライズの自動化
- Google App Script
### 基盤利用状況の監視
- Stackdriver

## ● freee

## ● リブセンス

## ● VASILY (Start Today Technologies)
Fluentd
embulk
BigQuery
Tableau
AirFlow
incubator
メインインフラはAWS

## ● Retty

## ● Gunosy

## ● Recruit Lifestyle

## ● DeNA

---

# Cloud Services

## ■ Google Cloud Platform
### ○ Compute Engine
Googleインフラストラクチャ上で仮想マシン(VM)を作成して実行できる

### ○ Kubernetes Engine
コンテナ化されたアプリケーションをデプロイするためのマネージド環境
 - アプリケーションやサービスを簡単にデプロイ、更新、管理できる
 - 可用性の高いサービスを実現し、シームレスな操作性を提供することができる
 - 1台のマシンから数千台のマシンまで、適切なタイミングで稼働させることが可能

### ○ App Engine
Googleのインフラストラクチャ上でスケーラブルなウェブバックエンドやモバイルバックエンドを構築
 - 追加設定なしで Node.js、Java、Ruby、C#、Go、Python、PHP をサポート
 - 通常はフルマネージドの恩恵を受けながら、必要に応じてインフラストラクチャにアクセスして高度にコントロールすることができる

### ○ Cloud SQL
GoogleCloudPlatform上のリレーショナルデータベースの設定、保守、運用、管理
 - MySQL または PostgreSQL で使用

### ○ Datastore
ウェブ、モバイルアプリケーションのためのスケーラビリティの高いNoSQLデータベース
 - シャーディングとレプリケーションを自動的に処理
 - App Engine と Compute Engine に拡張されたソリューションを構築し、統合ポイントを Cloud Datastore に置くことができる
 - データに応じてシームレスかつ自動的にスケールする

### ○ Cloud Storage
ライブデータの配信からデータ分析や ML、データ アーカイブまで、さまざまな用途に使用できる
 - Multi-Regional
 - Regional
 - Nearline
 - Coldline

### ○ Stackdriver Logging
ログデータやイベントを格納、検索、分析、モニタリング、通知
 - Google Cloud Platform と Amazon Web Services で実行されるアプリケーションに対応

### ○ Dataflow
ストリーム データ処理とバッチデータ処理を簡素化
 - 予測分析の統合ポイントとして役立つ

### ○ Pub/Sub
シンプルで信頼性の高いリアルタイムのストリーム分析を実行
 - ストリーム分析とイベント駆動型コンピューティングシステム向けの、シンプルで信頼性の高いスケーラブルな基盤として機能

### ○ Bigtable
NoSQLビッグデータデータベースサービス
 - データ規模やアプリケーションの種類にかかわらず、低レイテンシで高スループットを実現
 - 数百ペタバイトまでも自動的にプロビジョニングとスケーリングを行い、毎秒数百万のオペレーションを滞りなく処理

## ■ Amazon Web Service
### ○ Simple Queue Service
### ○ Lambda
### ○ EC2 Auto Scaling

## ■ Microsoft Azure

---

# Hadoop

## ■ MapReduce
## ■ Tez
## ■ Spark
## ■ Impala

---

# BI tools

## ■ Tableau
## ■ Power BI
## ■ b-dash

---

# Other tools

## ■ Fluentd
## ■ Embalk
## ■ Digdag
## ■ Talend
## ■ Alteryx
## ■ Tresure Data
## ■ Data Robot
