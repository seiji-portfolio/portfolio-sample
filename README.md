# UEP v5.0 – Unified Enterprise Platform
**100+ モジュールを統合したエンタープライズ向け API / データ / イベント基盤**

---

## 🎥 Demo（39秒）
プロダクト全体の動作を 39 秒にまとめたデモ動画です。  
（※ 面談時に URL を共有）

---

## 📘 Overview（概要）
UEP v5.0 は、API 基盤・データ基盤・イベントストリーミング・監視・MLOps を  
**1つの統合アーキテクチャとして構築したエンタープライズ向けプラットフォーム** です。

- FastAPI を中心とした API 設計・実装  
- PostgreSQL / Redis / MinIO を用いたデータ基盤  
- Kafka によるイベントストリーミング  
- Prometheus / Grafana / Jaeger による監視・トレーシング  
- Docker Compose によるローカル統合環境  
- 100 以上の API / モジュールを統合した構造  

---

## ■ Architecture（アーキテクチャ）
※ GitHub には簡易図を掲載（詳細図は面談時に提示）

本システムは、クライアントからのリクエストを API Gateway（Kong/Envoy）で受け付け、  
認証・認可・ルーティングを行った上で FastAPI に転送する構成となっています。

FastAPI はアプリケーション層として、以下の複数のデータストアと連携します。

- **PostgreSQL**：トランザクションデータや永続データを管理  
- **Redis**：セッション管理・キャッシュ・高速参照用データを保持  
- **MinIO**：ファイル・バイナリデータ・ETL 中間生成物の保存

アプリケーション層で発生したイベントは **Kafka** に Publish され、  
非同期処理として Consumer がイベントを購読します。  
Consumer では、データ正規化・フィルタリング・集約などの **ETL 処理** を実行し、  
最終的に **Data Lake（MinIO またはオブジェクトストレージ）** に蓄積します。

これにより、API レイヤーとバッチ/分析レイヤーを疎結合に保ちながら、  
リアルタイム性とスケーラビリティを両立したデータパイプラインを構築しています。

運用監視については以下の構成です。

- **Prometheus**：FastAPI、Kafka、Consumer、DB などのメトリクスを収集  
- **Grafana**：Prometheus のメトリクスを可視化し、ダッシュボードとして提供  
- **Jaeger**：API Gateway → FastAPI → DB/Kafka の分散トレーシングを実施  
- **ELK（Elasticsearch / Logstash / Kibana）**：アプリケーションログ・イベントログを集中管理

これらにより、API のレスポンス遅延、Kafka の遅延、Consumer の処理詰まり、  
DB の負荷状況などをリアルタイムに可視化し、  
障害発生時のトラブルシューティングを迅速に行える運用基盤を実現しています。


```

---

## 📚 Tech Stack（技術構成）

### Backend / API
- FastAPI  
- Python  
- OpenAPI  
- Kong / Envoy（認証・認可）

### Data / Storage
- PostgreSQL  
- Redis  
- MinIO  
- ETL / Data Lake

### Event Streaming
- Kafka（Producer / Consumer / Topic 設計）

### Monitoring / Logging
- Prometheus  
- Grafana  
- Jaeger  
- ELK Stack  

### Infrastructure
- Docker / Docker Compose  
- Vault（Secrets 管理）

### Quality
- Playwright（E2E テスト）  
- Locust（負荷試験）  

---

## 🔍 Key Features（主要機能）

### ✔ API 基盤
- FastAPI による高速 API  
- OpenAPI 自動生成  
- 認証・認可（Kong / Envoy）

### ✔ データ基盤
- PostgreSQL / Redis / MinIO  
- スキーマ設計  
- ETL パイプライン

### ✔ イベント基盤
- Kafka による非同期処理  
- Producer / Consumer  
- Topic 設計

### ✔ 監視・運用基盤
- `/metrics` → Prometheus  
- `/targets` → Scrape 状況  
- Grafana ダッシュボード  
- Jaeger トレーシング  

---

## 🖥 Screenshots（画面例）
※ ロゴなしの画面を掲載  
- FastAPI `/docs`  
- Prometheus `/metrics`  
- Prometheus `/targets`  
- Grafana ダッシュボード  
- Jaeger トレース画面  

---

## 🚀 Development Flow（開発フロー）
1. 設計（AI 補助）  
2. API 実装  
3. DB / スキーマ設計  
4. Kafka イベント設計  
5. 監視・ログ基盤構築  
6. E2E / 負荷テスト  
7. デモ動画作成  

---

## 👤 Author（開発者）
**小川 清志（Seiji Ogawa）**  
AI R&D Engineer / Backend / Data / Event Streaming  

- LAPRAS：https://lapras.com/public/AEKCECT  
- Zenn：https://zenn.dev/seiji_ogawa  
- Qiita：https://qiita.com/seiji0514  

---
