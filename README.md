UEP v5.0 – Unified Enterprise Platform
100+ モジュールを統合したエンタープライズ向け API / データ / イベント基盤

🎥 Demo（39秒）
プロダクト全体の動作を 39 秒にまとめたデモ動画です。
（※ 面談時に URL を共有）

🏗 Overview（概要）
UEP v5.0 は、API 基盤・データ基盤・イベントストリーミング・監視・MLOps を
1つの統合アーキテクチャとして構築したエンタープライズ向けプラットフォーム です。

FastAPI を中心とした API 設計・実装

PostgreSQL / Redis / MinIO を用いたデータ基盤

Kafka によるイベントストリーミング

Prometheus / Grafana / Jaeger による監視・トレーシング

Docker Compose によるローカル統合環境

100 以上の API / モジュールを統合した構造

🧩 Architecture（アーキテクチャ）
※ GitHub には簡易図を掲載（詳細図は面談時に提示）

コード
Client → API Gateway → FastAPI → DB / Cache / Object Storage
                     → Kafka → Consumer → ETL → Data Lake
Monitoring: Prometheus / Grafana / Jaeger / ELK
📚 Tech Stack（技術構成）
Backend / API
FastAPI

Python

OpenAPI

Kong / Envoy（認証・認可）

Data / Storage
PostgreSQL

Redis

MinIO

ETL / Data Lake

Event Streaming
Kafka（Producer / Consumer / Topic 設計）

Monitoring / Logging
Prometheus

Grafana

Jaeger

ELK Stack

Infrastructure
Docker / Docker Compose

Vault（Secrets 管理）

Quality
Playwright（E2E テスト）

Locust（負荷試験）

🔍 Key Features（主要機能）
✔ API 基盤
FastAPI による高速 API

OpenAPI 自動生成

認証・認可（Kong / Envoy）

✔ データ基盤
PostgreSQL / Redis / MinIO

スキーマ設計

ETL パイプライン

✔ イベント基盤
Kafka による非同期処理

Producer / Consumer

Topic 設計

✔ 監視・運用基盤
/metrics → Prometheus

/targets → Scrape 状況

Grafana ダッシュボード

Jaeger トレーシング

🖥 Screenshots（画面例）
※ ロゴなしの画面を掲載

FastAPI /docs

Prometheus /metrics

Prometheus /targets

Grafana ダッシュボード

Jaeger トレース画面

🚀 Development Flow（開発フロー）
設計（AI 補助）

API 実装

DB / スキーマ設計

Kafka イベント設計

監視・ログ基盤構築

E2E / 負荷テスト

デモ動画作成

👤 Author（開発者）
小川 清志（Seiji Ogawa）  
AI R&D Engineer / Backend / Data / Event Streaming

LAPRAS：https://lapras.com/public/AEKCECT

Zenn：https://zenn.dev/seiji_ogawa

Qiita：https://qiita.com/seiji0514

---

## 主な実装実績（参考）

- エンタープライズ統合プラットフォーム（稼働率99.995%、推論レイテンシ10ms未満）
- MLOps/LLMOps基盤、生成AI（RAG、CoT推論）
- インクルーシブ雇用AI（障害者雇用マッチング・アクセシビリティ特化）
- Webアクセシビリティ検査員検定 レベル1〜3 認定

---

## 連絡先

- **Email**: kaho052514@gmail.com

---

*本リポジトリは応募用のサンプルです。詳細な実装は面談時にデモンストレーションでご確認いただけます。*
