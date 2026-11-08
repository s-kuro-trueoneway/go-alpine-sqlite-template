# Go Alpine SQLite Template

Go、Alpine.js、SQLite を使ったシンプルな SSR Web アプリケーションの雛形です。

## 概要

このプロジェクトテンプレートは以下の技術スタックを採用しています：

- **Backend**: Go (net/http, html/template, database/sql)
- **Frontend**: HTML5, CSS3, Vanilla JavaScript, Alpine.js
- **Database**: SQLite

**主な特徴**：
- Server-Side Rendering (SSR) アプリケーション
- 最小限の依存関係（Go 標準ライブラリ中心）
- 読みやすく、保守しやすいコード構造
- セキュリティを考慮した実装

## ディレクトリ構造

```
.
├── cmd/
│   └── server/
│       └── main.go          # アプリケーションエントリーポイント
├── internal/
│   ├── handler/             # HTTPハンドラ（リクエスト/レスポンス）
│   ├── service/             # ビジネスロジック
│   ├── repository/          # データベースアクセス
│   ├── model/               # ドメインモデル
│   └── database/            # DB接続管理
├── web/
│   ├── templates/
│   │   ├── layouts/         # レイアウトテンプレート
│   │   ├── components/      # 再利用可能なコンポーネント
│   │   └── pages/           # ページ固有のテンプレート
│   └── static/
│       ├── css/             # スタイルシート
│       ├── js/              # JavaScriptファイル
│       └── img/             # 画像リソース
├── migrations/              # データベースマイグレーション
├── data/                    # DBファイル、設定ファイルなど
├── go.mod                   # Goモジュール定義
└── AGENTS.md                # AI開発者向け指示書
```

## 開始方法

### 前提条件

- Go 1.21 以上
- SQLite3（システムにインストールされていること）

### セットアップ

1. リポジトリをクローン：

```bash
git clone <repository-url>
cd go-alpine-sqlite-template
```

2. 依存関係を取得：

```bash
go mod tidy
```

3. アプリケーションを実行：

```bash
go run ./cmd/server/main.go
```

4. ブラウザで `http://localhost:8080` を開いてください。

## 開発ガイド

### コード規約

このプロジェクトでは `AGENTS.md` に定められた以下の原則を遵守してください：

- Go標準ライブラリを優先
- シンプルさを最優先（KISS、YAGNI）
- SQLインジェクション対策（プレースホルダ使用）
- XSS対策（html/templateの自動エスケープ）
- CSRF対策（必要なフォームにトークン）

### テスト

```bash
go test ./...
```

### フォーマットと検証

```bash
go fmt ./...
go vet ./...
```

## 技術スタックの詳細

### Backend (Go)
- `net/http` - HTTPサーバーとルーティング
- `html/template` - サーバーサイドレンダリング
- `database/sql` - データベース操作
- `context` - コンテキスト渡し
- `log/slog` - ログ出力

### Frontend
- **HTML5/CSS3** - 表示構造とスタイル
- **Alpine.js** - 軽量なUIインタラクション（モーダル、ドロップダウンなど）
- **Vanilla JavaScript** - Alpine.jsでカバーできない場合

### Database
- **SQLite** - サーバー内データベース
- 外部キー制約の有効化
- PRAGMA設定によるパフォーマンス調整

## 追加リソース

- [Go公式ドキュメント](https://pkg.go.dev/std)
- [Alpine.js公式ドキュメント](https://alpinejs.dev/)

## ライセンス

このテンプレートは自由に使用・改変できます。
