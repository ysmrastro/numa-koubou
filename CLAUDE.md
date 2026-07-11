# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## プロジェクト概要

「沼のほとり工房」— 天体観測まわりの3Dプリント製パーツを製作・紹介するWebサイト。
天文ファンコミュニティ「沼のほとり」から派生したサブブランド。GitHub Pages + Jekyll で静的サイトとしてホスティング。

- サイトURL: https://ysmrastro.github.io/numa-koubou/
- テーマ: [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/)（remote_theme、ダークスキン）
- 姉妹サイト: 沼のほとり（../numanohotori）— 配色・ロゴを共通化している

## 開発コマンド

```bash
bundle install
bundle exec jekyll serve   # → http://localhost:4000/numa-koubou/
```

テストやリンター等の設定はない。変更確認はローカルプレビューで行う。

## アーキテクチャ

### ページ構成

- `index.md` — トップページ（`home` レイアウト。商品グリッドを表示）
- `about.md` — 工房について

### 商品データ

- `_data/products.yml` — 商品一覧。1商品 = 1エントリ
  - `status`: `available`（販売中）/ `preparing`（準備中）/ `soldout`（完売）
  - `shop_url`: 販売ページURL。記入すると「購入ページへ」ボタンが出る（現状は決済導線 未定）
  - 商品画像は `assets/images/products/` に配置し `image` にファイル名を指定
- `_layouts/home.html` — 商品グリッドの描画ロジック

### ナビゲーション

`_data/navigation.yml` でヘッダーナビを定義。

### カスタマイズ

- `assets/css/custom.scss` — Minimal Mistakes のスタイル上書き（夜空テーマ `#0d1117`、リンク色 `#7eb8da`、商品カード `.product-*`）
- `_includes/head/custom.html` — favicon 設定

### ブランド資産

ロゴ・favicon は姉妹サイト「沼のほとり」と共通。原本は numanohotori/_brand/ にある。

### デプロイ

main ブランチへの push で GitHub Pages が自動ビルド・デプロイ。

## メモ

- 決済導線は未定。当面は商品紹介ページとして運用し、販売先（BOOTH 等）が決まったら
  各商品の `shop_url` にリンクを入れる方針。
