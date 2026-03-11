# /dev — Claude Code フルスタック開発スキル

仕様書を貼るだけで、**開発 → デプロイ → スプレッドシート同期 → 納品書作成**まで全自動で完了する Claude Code カスタムスキルです。

## 特徴

- **質問ゼロ** — 全てYESで判断し、完成まで止まらない
- **一気通貫** — 開発からデプロイ、納品書まで `/dev` 一発で完了
- **ブランドデザイン準拠** — ダークテーマ、モバイルファースト、日本語改行制御
- **セキュリティ対策込み** — zod バリデーション、bcrypt、Rate Limiting 等

## 実行フロー

```
/dev + 仕様書

PHASE 1: 開発
├── 仕様理解 → プロジェクト初期化 (Next.js + TypeScript + Tailwind)
├── DB設計 → API実装 → フロントエンド実装 (MongoDB + Mongoose)
├── セキュリティチェック
├── Google Spreadsheet 同期スクリプト生成
└── ビルド確認

PHASE 2: デプロイ
├── GitHub (private) にプッシュ
├── Vercel デプロイ
└── 環境変数を Vercel に設定

PHASE 3: 納品書
├── スクリーンショット自動取得
├── Reveal.js 納品書スライド (delivery-slides.html) 生成
└── 再デプロイ

→ 最終報告（URL・機能一覧・残件）
```

## 技術スタック

| カテゴリ | 技術 |
|---|---|
| フロントエンド | Next.js (App Router), React, TypeScript, Tailwind CSS |
| バックエンド | Next.js API Routes |
| データベース | MongoDB (Mongoose) |
| 認証 | bcryptjs, JWT, NextAuth.js |
| デプロイ | Vercel + GitHub |
| シート同期 | Google Sheets API (googleapis) |
| 納品書 | Reveal.js (単一HTML) |

## インストール

### ユーザーレベル（全プロジェクトで使用可能）

```bash
# 1. クローン
git clone https://github.com/YOUR_USERNAME/claude-dev-skill.git

# 2. スキルファイルをコピー
mkdir -p ~/.claude/commands
cp claude-dev-skill/.claude/commands/dev.md ~/.claude/commands/dev.md
```

### プロジェクトレベル（特定プロジェクトのみ）

```bash
# プロジェクトルートで実行
mkdir -p .claude/commands
cp claude-dev-skill/.claude/commands/dev.md .claude/commands/dev.md
```

## 使い方

Claude Code を起動し、以下のように実行:

```
/dev

[ここに仕様書を貼り付け]
```

## 前提条件

- [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code) がインストール済み
- Node.js 18+
- Git, GitHub CLI (`gh`), Vercel CLI (`vercel`)
- MongoDB Atlas アカウント

## 納品書サンプル

Reveal.js ベースのスライド形式で自動生成されます:

- タイトル → 概要 → 機能一覧テーブル → ページ階層図 → 各画面スクショ → 技術スタック → データモデル → セキュリティ → クロージング

## ライセンス

MIT
