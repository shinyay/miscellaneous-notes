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
