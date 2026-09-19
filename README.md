# Project Innovation | 集大成コーポレートサイト

株式会社プロジェクト・イノベーションの集大成コーポレートサイトです。
代表取締役 古谷幸治が掲げる「人と事業をクリエイトする」というテーマのもと、
**BtoB CRM／経営DX事業**（eMplexシリーズ）と**テレビ通販・ブランドプロデュース事業**という
二つの事業軸を1枚のLPにまとめています。

静的HTMLのみで完結しており、ビルド不要です。

## 公開方法（GitHub Pages）

1. このリポジトリをそのまま GitHub にプッシュします（下記コマンド参照）。
2. GitHub上でリポジトリの **Settings → Pages** を開きます。
3. **Source** を `Deploy from a branch` に設定し、Branch を `main` / フォルダを `/(root)` に設定して **Save** します。
4. 数分後、`https://<ユーザー名>.github.io/<リポジトリ名>/` で公開されます。

## 独自ドメイン（project-innovation.jp）を使う場合

リポジトリ直下に `CNAME` ファイル（中身は `project-innovation.jp` の1行のみ）を同梱済みです。
GitHub Pages 側の設定に加えて、ドメインの管理画面（お名前.com／ムームードメイン等のDNS設定）で以下のレコードを追加してください。

**ルートドメイン（project-innovation.jp）を使う場合 — Aレコードを4つ追加**

| タイプ | ホスト名 | 値 |
|---|---|---|
| A | @（空欄でも可） | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |

**www.project-innovation.jp も使う場合 — CNAMEレコードを追加**

| タイプ | ホスト名 | 値 |
|---|---|---|
| CNAME | www | `<ユーザー名>.github.io` |

設定後、GitHubの **Settings → Pages → Custom domain** に `project-innovation.jp` を入力して **Save**。
DNSが反映されたら（数分〜数時間）、**Enforce HTTPS** にチェックを入れてください（GitHubが自動でSSL証明書を発行します）。

## ローカルで確認する場合

`index.html` をブラウザで直接開くか、簡易サーバーを立てて確認できます。

```bash
python3 -m http.server 8000
# http://localhost:8000 にアクセス
```

## 構成

```
.
├── index.html                     # 統合コーポレートサイト（会社概要・BtoB CRMサービス・テレビ通販サービス・代表プロフィール）
├── jarvis-lp.html                   # eMplex J.A.R.V.I.S.（概要LP）
├── jarvis-full-wireframes.html      # eMplex J.A.R.V.I.S.（全モジュール ワイヤーフレーム, L0〜L6）
├── emplex-pbm.html                  # eMplex PBM 製品サイト
├── emplex_ma.html                   # eMplex MA
├── emplex_timesheet_lp.html         # eMplex タイムシート（LP）
├── emplex_timesheet.html            # eMplex タイムシート（アプリ画面）
├── emplex_forecast_lp.html          # eMplex フォーキャスト
├── emplex-mail-sales-lp.html        # eMplex Mail Sales（詳細LP）
├── emplex-mail-sales.html           # eMplex Mail Sales（アプリ画面）
├── frontier_dashboard_lp.html       # Frontier Dashboard
├── frontier_crm_luxury.html         # Frontier CRM（高級資産運用向けCRM）
├── tpm-career-lp.html               # eMplex TOKYO PRO Market（人材紹介）
├── jinmyaku-no-mori.html            # 人脈の森（人脈可視化アプリ）
├── ipo-consortium.html              # 次世代IPOコンソーシアム（Podcast/Network）
├── assets/furuya-koji.jpg           # 代表 古谷幸治 プロフィール写真
├── assets/logo.png                  # コーポレートロゴ（背景透過）
├── CNAME                            # 独自ドメイン設定（project-innovation.jp）
└── README.md
```

`index.html` は全事業を1枚に統合したコーポレートサイトです。
「BtoB CRM事業を見る」ボタンでページ内の `#service-crm`（BtoB CRMサービス）セクションへ、
「テレビ通販サービスを見る」で `#service-tv`（テレビ通販サービス）セクションへスクロールします。
BtoB CRMサービス内のエコシステム図・全サービス一覧からは、上記の各プロダクトページへ直接リンクしています。
