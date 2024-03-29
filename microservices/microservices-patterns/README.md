# Microservice Patterns

- [Microservices Patterns With examples in Java](https://www.manning.com/books/microservices-patterns)

## Description
### アーキテクチャ
#### Monolithic Architecture
単一コンポーネントによるアプリケーション構成パターン

##### 課題
- [Monolithic Hell](https://microservices.io/microservices/general/2018/11/04/potholes-in-road-from-monolithic-hell.html)

#### Microservice Architecture
独立してデプロイ可能なサービス群による疎結合なアプリケーション構成パターン

- 小規模チーム
- 最短リードタイム
- 最小チーム間連携コスト

#### Database per Service
サービス毎にプライベートなデータストアを持つ構成パターン

##### 備考
各サービスがデータベースを共有するパターン：Shared Database

### サービス分割
#### Decompose by Business Capability
ビジネス・ケイパビリティ単位でサービス分割するパターン

- ビジネス・ケイパビリティ
  - ビジネスの構成要素のWHAT

#### Decompose by SubDomain
**DDD のサブドメイン**単位でサービス分割するパターン

### メッセージング
#### Remote Procedure Invocation
`REST` や `gRPC` などによる**同期**で呼び出しするパターン

#### Messaging
クライアントからサービス宛のメッセージを**非同期**で送信するパターン

- ブローカベース
- ブローカレス

### 信頼性
#### Circuit Breaker
クライアントとサービスの間に **Circuit Breaker** と呼ぶプロキシを介在させて、サービスの呼び出し失敗が一定基準を超えると、クライアントからのリクエストを即座にリジェクトさせて、ブロッキング連鎖を解消するパターン

### サービスディスカバリ
#### Service Registry
サービスのインスタンスとネットワークロケーションの対応付けをデータベースに登録するパターン

#### Client-Side Discovery
クライアントがサービスレジストリを検索して使用可能なインスタンスのリストを受け取るパターン

### トランザクション
#### Transactional Outbox
トランザクションの中で、DB内のメッセージキューに見立てた "OUTBOX" テーブルにメッセージを入れるパターン

#### Polling Publisher
OUTBOX を定期ポーリングしてメッセージを発行するパターン

- パフォーマンスや負荷の面で望ましくない場合あり

#### Transaction Log Tailing
OUTBOX テーブルのトランザクションログを tail してメッセージを発行するパターン

- DB製品ごとに異なる低レベルコードの実装が必要

### データ整合性
#### Saga
各サービスのローカルトランザクションを、非同期メッセージングでつなげてフローを構成するパターン

- フロー・タイプ
  - コリオグラフィー型: シンプルなフロー
    - 各サービスが互いの実行結果に応じて協調して処理を実行し、最終的にワークフローを完遂する
  - オーケストレーション型: 複雑なフロー
    - 中央集権的なオーケストレータがサーガの進行を管理する
- ローカル・トランザクション
  - Compensatable Transaction
    - 補償可能な (状況に応じて後で変更を打ち消すことができる) ローカルトランザクション
    - Compensating Transaction と対になる
  - Compensating Transaction
    - 実行済み Compensatable Transaction と逆順で実行される
  - Pivot Transaction
    - Compensatble と Retriable の境界に位置するローカルトランザクション
  - Retriable Transaction
    - ロールバック不要で成功が保証されているローカルトランザクション

### ビジネスロジック
#### Aggregate
Aggregate を整合性の境界とするパターン

- １Aggregate :１トランザクション

#### Domain Event
Aggregate が生成・変更された時に非同期メッセージを発行するパターン

#### Domain Model
ビジネスロジックを状態とふるまいを持つクラス群から成るオブジェクト指向的なドメインモデルで構成するパターン

#### Event Sourcing
Aggregate の永続化を Domain Event のシーケンスとして表現するパターン

- Saga や CQRS と併用
- Audit Logging

### クエリー
#### CQRS (Command Query Responsibility Segregation)
コマンドサイドとクエリサイドで、別々にモデルとデータストアを用意して、イベントハンドラで同期するパターン

#### API Composition
複数サービスへのアクセスと、そのレスポンスの組み立てをAPI Composerが行うパターン

### 外部API
外部クライアントからのアクセスの受口
- Web アプリケーション
- JavaScript
- モバイルアプリケーション
- 公開API
- など

#### API Gateway
システムの窓口に、Facadeコンポーネントを置くパターン
- API Composition
- プロトコル変換
- クライアント専用API
- など

#### Backends for Front-Ends
外部APIクライアントのために、専用の API Gateway を置くパターン

### 監視
#### Health check API
生存確認用のエンドポイントをサービスに持たせるパターン

#### Log Aggregation
全てのサービスのログを検索機能やアラート機能を持つロギングサーバに集中するパターン

#### Distributed Tracing
外部からのリクエストにユニークIDをふって複数マイクロサービス間にわたるワークフローのログ出力を可視化・分析機能を持った分散トレーシングサーバに集めるパターン

#### Application Metrics
アプリケーションの各種メトリクスを、集約、可視化、アラート機能をもったメトリクスサービスに集めるパターン

#### Exception Tracking
例外ログを、重複除去や対応状況管理などの機能を持つ例外トラッキング用のサービスに、レポートするパターン

### リファクタリング
#### Strangler Application
モノリスの周囲にインクリメンタルにマイクロサービスを作って、徐々にモノリスの機能を吸収していくパターン
- 新規機能をマイクロサービスとして作る戦略
- フロントエンドを切り離す戦略
- 既存機能を切り出してマイクロサービスとする戦略

#### Anti-Corruption Layer
防腐レイヤーを挟んで、洗練させた新モデルと旧モデルの差分を吸収するパターン

## Demo

## Features

- feature:1
- feature:2

## Requirement

## Usage

## Installation

## Licence

Released under the [MIT license](https://gist.githubusercontent.com/shinyay/56e54ee4c0e22db8211e05e70a63247e/raw/34c6fdd50d54aa8e23560c296424aeb61599aa71/LICENSE)

## Author

[shinyay](https://github.com/shinyay)
