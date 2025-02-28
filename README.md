# skill-typing-infra-CloudFormation（作成中）
ハッカソン2025冬 Aチームインフラ用リポジトリ

## 今回作成したAWS構成図について
詳細は省略しますが、今回は受講しているITスクールで、以下のようなAWSインフラ構成をコード化しています。

### 📌 構築するインフラ構成図

![Screenshot 2025-02-21 at 7.29.34.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/3662571/14c68cef-7863-4742-97de-dc012a8dfd49.png)

VPC（Virtual Private Cloud）
- AWS 上で独立したネットワーク環境を構築
- CIDR ブロックの指定
- サブネットの分割（パブリック / プライベート）

サブネット
- **パブリックサブネット**：インターネットへのアクセスが可能
- **プライベートサブネット**：インターネットからの直接アクセスを制限

インターネットゲートウェイ / NAT ゲートウェイ
- **インターネットゲートウェイ（IGW）**：パブリックサブネットからの外部通信を許可
- **NAT ゲートウェイ**：プライベートサブネットからの外部通信を許可

ECS（Elastic Container Service）
- AWS Fargate によるコンテナ管理
- タスク定義（Task Definition）の作成
- サービスのデプロイ（ECS Service）
- ALB（Application Load Balancer）との統合

ALB（Application Load Balancer）
- ECS サービスのロードバランシング
- **ターゲットグループ** の設定
- **リスナー** の設定（HTTP / HTTPS）
- **ヘルスチェック** の構成

RDS（Relational Database Service）
- MySQL 8.0 のデータベースを作成
- **パラメータグループ** の設定
- **セキュリティグループ** によるアクセス制御
- **Secrets Manager** によるパスワード管理

CloudFront & S3

S3（Simple Storage Service）
- React アプリのホスティング
- **バケットポリシー** の設定
- **OAI（Origin Access Identity）** によるアクセス制御

CloudFront（CDN）
- S3 をオリジンとしたコンテンツ配信
- **キャッシュポリシー** の設定
- **カスタムドメイン**（オプション）

### 💬 問い合わせ
質問や問題がある場合は、GitHub の Issues または Pull Request でお問い合わせください。

