# Name

Overview

## Description
### OSS テクノロジー
- Kubernetes
- Istio
- Knative

### Migrate for Anthos
`物理サーバー、オンプレミスの VM、Compute Engine VM、その他のクラウドで動作するVM` to **Google Kubernetes Engine（GKE） コンテナ**

### Anthos プラットフォーム
#### CI/CD
##### Cloud Build
- GitHub、Cloud Source Repositories、Bitbucket リポジトリに変更を push したときに、自動的にソースコードのビルド、テスト、デプロイが行われる
- Maven、Gradle、Webpack、Go、Bazel などのビルドツール でパッケージング
- Deploy to Kubernetes Engine、App Engine、Cloud Functions、Firebase
- ローカル / クラウドビルド

##### Container Registry
- 安全な非公開 Docker レジストリ
- コンテナイメージの脆弱性スキャン
- リスクのあるイメージを自動ロックダウン

#### Serverless
##### Cloud Run with GKE
- Knative on GKE
- HTTP リクエスト経由で呼び出し可能なステートレス コンテナ
- トラフィックに応じてゼロから N までのオートスケール

#### Marketplace
##### GCP Marketplace
- Anthos による統合
- `ビッグデータ`、`アナリティクス`、`ネットワーキング`、`セキュリティ`、`データベース`、`開発ツール` など
  - `GitLab`, `CloudBees`, `Neo4j`, `Seldon`, `Aerospile`, `Couchbase`, `Elastifile`, `WordPress`, `Prometheus` など

#### API監理
##### Apigee
- オンプレミス、クラウド、マルチクラウド、ハイブリッド環境を選択
- 内部 API と外部 API のすべてを 1 つのプラットフォームで管理

#### Observability
##### Stackdriver
- ログ、メトリクス、トレース、アラート
- Google Cloud Platform、Amazon Web Services、オンプレミス

##### Google Cloud Service Mesh

### Istio
- ロードバランシング：HTTP, gRPC, WebSocket, MongoDB, and TCP
- トラフィックコントロール：routing rules, retries, failovers, and fault injection.
- ポリシー設定：access controls, rate limits, and quotas.
- メトリクス、ログ、トレース
- サービス間通信


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
