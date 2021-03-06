# ■ スモールスタート後に参画、普及期を経験して得た気づき
データマートの設計、開発、運用を担う少人数（〜２人）の部隊で、普及期から参画して得た気づき。

## ◆ BIツールの明確なニーズと普及の道筋を見通しておく重要性
**データによる意思決定が可能な環境を整えることで、BIツールの導入・運用コストを上回る利益増加・コスト削減を実現する必要がある。**  
BIツールの導入には様々なコストがかかり、普及するに伴い必要なリソースは拡大していく。
- 導入コスト
  - 分析基盤の構築にかかる人件費
  - 分析基盤の利用料
  - ツールのライセンス料
  - 技術者、アナリストの初期学習コスト
- ランニングコスト
  - 分析基盤の保守費用（インフラ利用料、人件費）
  - ツールのライセンス料
  - サードパーティ製のデータ購入費
- 利用者のラーニングコスト
  - 講習の受講料（もしくは社内研修やQA対応にかかる人件費）
また、普及に向けた道筋を見通しておく必要がある。スモールスタートにあたり、まず事業のどの部分にフォーカスして可視化を進めていくかを定め、段階的に可視化領域を広げていくにあたって必要なリソースや起こりうる問題を予め予測しておく必要がある。  
実施に目の当たりにした問題は下記の通り。
- 事業を統括する部署向けに作ったデータマートが拡散し、当初の目的以外の領域でも利用され始める
  - 同一の指標に見えても、組織ごとに定義が異なる場合がある
  - 組織ごとに異なるディメンションのカテゴライズロジックが存在している場合がある
  - 指標の厳密さを求めずに実用化している場合があり、数値に関する調査依頼が発生する
  - 想定していた利用範囲を超えて活用（事業所への配布など）するユーザが発生する
  - リテラシーの低いユーザによるツールの使用方法に関するQAが増加する
- 様々な組織の切り口で同一のデータマートに対する改修依頼が発生する
  - データマートが肥大化し、使用とメンテナンスの両面でパフォーマンスが低下する
  - 開発・保守にかける人的リソースが限られたまま、データマートは増加していく

## ◆ 分掌を定義しておく重要性
**責任の所在を明確にしておく。**  
離職や人事異動が発生すると、属人化していた責任意識の消失や、後任者による責任所在の外部への転化が発生する恐れがある。  
大きな組織の場合、組織ごとに負う責任範囲と窓口を定義し、オープンな場所で公開しておくのが望ましい。
- 事業のコアとなる指標を定義する組織  
（データウェアハウス(汎用データマート)のオーナー）
- BIツールを活用する各事業領域ごとの組織（縦割りで部門間の壁がある場合もある）  
（施策やサービスに紐づく個別データマートのオーナー）
- データマートを設計、開発し、モニタリング環境を保守・運用する組織
- データ分析・活用基盤を保守・運用する組織
それほど規模の大きくない組織では、データ分析組織が下記の領域に責任を負うべきだと思う。
- モニタリングを見越したデータベース設計に対する助言
- KPIの設計に対する助言
- サーバサイドエンジニアとのコミュニケーションに基づく、データ取得元のテーブル構造と、データの抽出方法の定義

## ◆ 設計思想を共有する重要性
**汎用的に使われることが想定されるデータマート群は、設計思想を開発・保守担当者はもちろんのこと、事業サイドとも共有しておく。**  
キンボールのディメンショナルデータウェアハウス、スタースキーマの概念がTableauとの相性がいい。目的ごとにファクトテーブルを作成、各事業領域ごとの組織別にディメンションテーブルを準備し、ニーズに応じて拡張する。利便性を考慮し、ファクトテーブルには組織横断で活用する汎用的なデモグラフィックをディメンションを予め持たせておくのが望ましい。  
事業サイドに共有しておくのは、ファクトテーブルに必要な物が全て揃っている状態を志向する傾向が強い（Tableau上での結合処理を好まない）ため。

## ◆ ドキュメントの重要性
**データマートが作成された目的、利用者、利用頻度、使用するデータ取得元テーブルからの抽出条件、集計ロジックの要件、定期的なメンテナンスを要する箇所などをドキュメント化しておく。**  
BIツールの利用者と保守運用を要するデータマートは増加し続けるが、クエリの解析に使える時間は有限。ただし、詳しすぎるドキュメントはドキュメント管理の負荷も発生するため、属人化・ブラックボックス化すると困ること、ユーザーが把握すべきことをドキュメント化する。  
また、組織横断で有用に見えるデータマートは、知らず知らずのうちに仕様を理解せずに利用するユーザーが拡大していく。問い合わせの増加や仕様変更の周知に備え、ドキュメントの公開とオープンな場でのドキュメント管理が望ましい。

## ◆ モニタリング前後の業務を知る重要性
**作成したデータマートから得られるアウトプットは、どのような場面で業務に活用されているのかを把握しておく。**  
モニタリング基盤の障害発生時、集計値の狂いが定期更新処理のリリース後に見つかった場合、どのような影響がありそうかを知る必要がある。

## ◆ 依頼フロー設計の重要性
**プロジェクト管理ツールを導入し、その運用ルールを予め整備して、依頼フローを整えておく。**  
事業サイドには、把握が必須のものから担当者の興味レベルのものまで、異なる粒度で無数のニーズが存在する。BIツールが導入期を脱して普及期に入る前に、フレームワーク化しておくのが望ましい。データ分析・活用の組織形態と分掌は企業によって大きく異なると考えられるため、依頼のフローは柔軟に作り上げていく必要がありそう。
また、要件定義時のヒアリングを効率化するため、依頼時に提示してもらうべき事項は雛形を作成しておく。

## ◆ 開発フロー設計の重要性
**開発担当者間の意思疎通、事業サイドに必要工数への意識を持ってもらうため、開発工程を設計してオープンにしておく**  
データマートの開発は、システム開発ほどの経験値と高度なスキルは要求されず、経験のある人材も多くないことから、未経験に近い人材がアサインされる傾向がある。開発時に踏むべき工程に対する担当者の認識と意識レベルが大きく異なるため、開発フローを設計し、アサイン時にインプットする必要がある。使用するデータソースの初期確認事項からデータマート開発後の検算方法まで、現場に応じた枠組みを準備し、開発フローを設計しておくと良い。  
**ただし、業務のマニュアル化には一考の余地がある。マニュアルは作業者をデータエンジニアから単なるオペレータに育ててしまう懸念がある**

## ◆ 組織構造とそれぞれの役割を知る重要性
**組織の役割を知ることで、ユーザのニーズ（今後発生する拡張要件に先回りできる可能性）を掘り起こしておく**  
開発、テスト、リリース作業にかかる工数を削減するため、極力追加開発は避けたいため、要件定義時にニーズを掘り起こしておく。ただし、分析環境にかけられるコストは組織によって大きく異なるため、自由度高くダイナミックに構えられない場合は、優先順位をつけてテーブルのサイズをコントロールするテクニックが必須となる。

## ◆ データ収集の仕組みを知る重要性
**人による事務作業から発生するデータなのか、システム的に更新されていくデータなのかを把握しておく**  
人による事務作業が更新の起点となっている場合、実績値の反映までのタイムラグを意識しておく必要がある。またWebサービスや業務システムは、実際に触って見なければわからないこともあり（その機能は同一のページから利用可能なのか、機能ごとにページが用意されているのか、ユーザは意識しておらずシステム管理上の機能なのかなど）、分析の局面では重要な意味を持つことがある。

## ◆ BIツールの仕様を知る重要性
**ユーザが思い描く可視化や分析が、着実に実現可能となるようツールの仕様や機能を把握しておく**  
実際に作成したデータマートでダッシュボードの作成や分析をして見なければわからないこともある。操作性はサービス開発と一緒、使い勝手が悪ければ、利用者は減っていく。  
実際に、Tableauでは下記を実現するにはユーザの習熟度を上げる必要がある印象。
- 昨年同月比の可視化（LOOKUP関数の活用）
- LOD表現（FIXED,EXCLUDE,INCLUDE）の活用

**データマートの開発者が、ダッシュボードの作成まで担当できる組織体制が望ましい印象。**  
Bookにおいてはメジャーと表現(グラフの形式)は固定し、ユーザはフィルタ・ページ、ディメンションのみいじる運用が安定稼働しそう。

---

# モニタリングテーブル開発でもっと事業に貢献する

# ■ Tableauが果たしていくべき役割とは？
## ① 指標の定常的なモニタリングと分析
1. ダッシュボード化してモニタリング（TableauServer,TableuReaderの活用）
2. 指標の変動要因を分析（ドリルダウン）して課題を明確にする
3. 分析結果を施策（売上の改善, コストの削減）における意思決定に役立てる

## ② 定常的なレポーティング業務の高速化・自動化
- データのエクスポート処理の効率化
- レポーティングの自動化

# ■ 要件定義のポイント
## **新規開発**
### ◆ 利用者が実現したいこと
- 可視化の目的
  - 現状把握
  - 施策の検討（課題探索、仮説検証）
  - 要因把握
  - 施策の効果測定・効果予測
- 具体的なメジャー（指標）
  - 指標そのもの（メジャーを作成するのに必要な要素ではNG）
  - 指標の重要度（必須 or 興味）
- 具体的なディメンション（属性）
  - フィルタリングが目的なのか、内訳を見たいのか
  - 粒度（カテゴライズして抽象度を上げるべきか）
- アウトプット形式
  - グラフ（棒、折れ線、円、ヒートマップ、散布、積み上げ）
  - スプレッドシート

### 要件定義時に整理すること
**事業課題要件**

事業課題要件 | 内容
--|--
プロジェクト名 | 端的に、本質をついたネーミングにすること
依頼組織 | 組織名称
担当者（敬称略） | 担当者指名
組織のKGI | 依頼組織のKGI
背景 | 入力フォーム記入中に離脱してしまうユーザーが多く、CVを逃している
課題 | 離脱ユーザに対する再訪喚起メールの開封率と再訪率を分析できていない
施策 | Tableauで定期的に指標をモニタリングし、再訪喚起メールの送付を最適化する
本プロジェクトの達成条件(KPIと目標数値) | 再訪率 ＝ 再訪ユーザ数 / 一時保存ユーザ数
アウトカム | ① フォーム入力離脱ユーザの傾向の可視化 ② 喚起メールの最適化による開封率、再訪率の改善
期限 | 期限日


**分析要件**

分析要件 | 　 | 内容
--|--|--
分析目的 | 誰に | 組織単位
　 | 何の目的で | 現状把握、課題発見、要因把握、予測モデル作成、施策検証
　 | どんな情報を（指標） | 指標を構成する要素ではなく、指標そのもので
　 | どの切り口で（属性） | アクションを起こせるセグメントであるかを検討する
　 | どの頻度で | Q毎、月次、週次、日次など
　 | 意思決定により起こせる行動 | 具体的に起こせるアクション
アウトプット | 可視化 / アウトプット方法 | クロス集計、棒グラフ、折れ線グラフ、散布図など
　 | 分析手法 | 回帰、分類など
　 | アウトプットまでの工程 | モニタリングテーブルによる結合、分析ソフトウェアやOSSライブラリによる分析など


**データ要件**

データ要件 | 内容
--|--
データ粒度 | 主キー設定
抽出・結合条件 | セグメント、期間などの抽出条件。RDB上のテーブル結合による取得条件
必要カラム | メジャーの構成要素、ディメション
検証方法 | 検証方法とレビューの体制。正解データや比較・参考可能なデータがないか確認し、求められる精度と納期に応じてレベル感を調整
イテレーション検証方法 | 定常モニタリングの場合、イテレーション期間の検証方法も定義しておく


### ◆ モニタリングの前後にある業務、施策
- 業務の内容（運用の目的と業務フロー）
- 施策の内容

## **追加開発**
### ◆ 利用者が実現したいこと
- 既存テーブルの改良
  - 今、どう使っているのか
- 既存テーブルの転用
  - 妥当性の検討  
  （転用可能なのか、新規作成にすべきか）
- 具体的なメジャー（指標）
  - 指標そのもの（メジャーを作成するのに必要な要素ではNG）
  - 指標の重要度（必須 or 興味）
- 具体的なディメンション（属性）
  - フィルタリングが目的なのか、内訳を見たいのか
  - 粒度（カテゴライズして抽象度を上げるべきか）

## **保守に関する取り決め**
- 利用期間
- 利用予定者の範囲
- 手動でメンテナンスするロジックやマスタの有無
