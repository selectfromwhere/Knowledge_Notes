# Webサービスを提供する企業の分析基盤
下記の目的ごとに、企業内部でも異なる構成でデータ分析基盤が運用されている
- システムログ(オンプレ、クラウドサービス)の可視化、分析、監視
- イベントログの可視化、分析
- 機械学習

## ● Mercari
https://speakerdeck.com/cubicdaiya/mercari-data-analysis-infrastructure
http://tech.mercari.com/entry/2017/12/09/103000
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
### 分析基盤利用状況の監視
- Stackdriver

## ● Money Forward
https://www.slideshare.net/tetsuroito/dataops-in-moneyforward
### ログ収集、ストリーミング、ワークフロー
- embulk
- digdag
### ログの蓄積
- BigQuery
### ビジュアライズ
- Elasticsearch(+ kibana?)
- redash

## ● freee
https://speakerdeck.com/krtk2k/freee-falsedetafen-xi-ji-pan-nituite
### ログ収集、ストリーミング、ワークフロー
- embulk
- fluentd
- digdag
### ログの蓄積
- S3
- Redshift
- BigQuery
### ビジュアライズ
- GA 360 Suite
- Elasticsearch + Kibana
- redash

## ● リブセンス
https://speakerdeck.com/livesense/ribusensufalsedetafen-xi-ji-pan-falsequan-mao
### ログ収集、ストリーミング、ワークフロー
- fluentd
- embulk
- kinesis firehose
- EMR Spark
- Glue
- Airflow
### ログの蓄積
- S3
- Redshift
### ビジュアライズ
- redash
- Tableau
- Excel

## ● VASILY (Start Today Technologies)
http://tech.starttoday-tech.com/archive/category/%E3%83%87%E3%83%BC%E3%82%BF
### ログ収集、ストリーミング、ワークフロー
- fluentd
- embulk
- Puree
- AirFlow
- incubator
- Luigi
### ログの蓄積
- BigQuery
### ビジュアライズ
- Tableau
- SpreadSheet

## ● Retty
https://speakerdeck.com/jp_taku2/rettyfalsefen-xi-ji-pan-nituite-detafen-xi-ji-pan-night-number-1
https://speakerdeck.com/chie8842/rettyfalsefen-xi-ji-pan-niokeruawshuo-yong-shu
### ログ収集、ストリーミング、ワークフロー
- fluentd
- embulk
- kinesis Firehose
- EMR Spark
- AirFlow
### ログの蓄積
- S3
- BigQuery
### ビジュアライズ
- Tableau

## ● Gunosy
https://speakerdeck.com/moyomot/gunosyfalsedetafen-xi-ji-pan-roguji-pan-falsequan-rong
### ログ収集、ストリーミング、ワークフロー
- Fluentd
### ログの蓄積
- RedShift
- BigQuery
### ビジュアライズ
- redash

## ● FiNC
https://speakerdeck.com/yoshimikeisui/fincfalsefen-xi-ji-pan-falsegai-yao
### ログ収集、ストリーミング、ワークフロー
- kinesis firehose
- lambda
- fluentd
- AWS DMService
### ログの蓄積
- S3
- Redshift
### ビジュアライズ
- redash
- Excel

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

### ○ Firebase
Googleのインフラストラクチャ上で様々なプロダクトを組み合わせ、モバイルアプリを開発
 - インフラストラクチャの管理は不要
 - 状況に応じて自動的にスケーリング
 - プロダクト間のデータや分析情報の共有が可能

## ■ Amazon Web Service
### ○ S3
データの保存と取得が簡単に行えるオブジェクトストレージ
 - 高い耐久性、可用性、スケーラビリティー
 - 世界中の規制機関によるコンプライアンス要件を満たすセキュリティ、コンプライアンス機能
 - 分析システムに移動することなくビッグデータ分析が可能

### ○ RedShift
高速で完全マネージド型のデータウェアハウス
 - 標準SQLおよび既存のビジネスインテリジェンス(BI)ツールを使用可能
 - ペタバイト単位の構造化データに対して複雑な分析クエリを実行可能
設計時に、[ノードスライス][分散キー(DISTKEY)][ソートキー(SORTKEY)]の概念理解が重要

### ○ EMR
Apache Hadoop、Spark、HBase、Presto、Hive、その他のビッグデータフレームワークを簡単に実行してスケーリング
 - Apache Spark や HBase、Presto、Flink など他の一般的なフレームワークを実行
 - Amazon S3 や Amazon DynamoDB など他のAWSデータストア内でデータを操作

### ○ Lambda
サーバーのプロビジョニングや管理なしでコードを実行
 - 自動的にアプリケーションをスケール
 - コードを実行した回数、実行時間に応じて課金

### ○ Kinesis Data Firehose
ストリーミングデータをデータストアや分析ツールにロードする
 - スケーリング、シャーディング、モニタリングなど、ストリーム管理全般が提供される
 - Amazon S3、Amazon Redshift、Amazon Elasticsearch Serviceへのロードが可能
 - 独自のデータパイプライン処理構築は不要

### ○ Kinesis Data Streams

### ○ Kinesis Data Analytics

### ○ Simple Queue Service

### ○ Glue

### ○ Database Migration Service

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
## ■ Redash

---

# MA tools

## ■ Marketo
## ■ b-dash

---

# Other tools

## ■ Fluentd
## ■ Embalk
## ■ Talend
## ■ Alteryx


## ■ Digdag
## ■ Airflow


## ■ Tresure Data
## ■ Data Robot


salesforce
zendesk
zuora
LiveChat
NewRelic
bugsnag
mackerel
JIRA
makefile(データフローエンジン)
