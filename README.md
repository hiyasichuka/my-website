# 高橋慶 - Data Engineering Manager Portfolio

データエンジニアリングマネージャーの高橋慶のプロフェッショナルポートフォリオサイトです。

## 🌐 サイトを見る

**GitHub Pages (デフォルト):**  
https://hiyasichuka.github.io/my-website/

**カスタムドメイン（準備中）:**  
https://takahashi-kei.dev/

## 📚 ページ構成

### ホームページ

- 自己紹介とキャッチフレーズ
- 専門分野（Data Infrastructure）
- テックスタック概要
- 認定資格一覧

### プロジェクト実績

1. **ペタバイト超のデータ基盤移行プロジェクト** (DMM.com)
   - Google Cloud への移行
   - IaC 自動化による構築
2. **エンジニアリングマネジメント体制構築**

   - チーム統括・育成
   - Google Cloud との技術連携

3. **BigQuery + Looker 分析基盤**

   - BI ツール運用

4. **システム開発 & テックリード経験**
   - Vue.js、NestJS、FastAPI での開発

### スキル・経歴

- プログラミング言語（Python、TypeScript、SQL 他）
- クラウドインフラ（GCP、AWS、Azure）
- データ処理・パイプライン（Airflow、Embulk、Digdag）
- BI・データ可視化（Tableau、Looker）
- 公式資格（Google Cloud、AWS、IPA）

## 🎨 デザイン特徴

- **モダンで個性的** - 紫～青のグラデーション背景
- **ダークモード対応** - 目に優しいダークテーマ
- **スムーズなアニメーション** - フェードイン・浮動効果
- **レスポンシブ対応** - モバイル・デスクトップ対応
- **高速** - Hugo による静的サイト生成

## 🛠️ 技術スタック

- **静的サイトジェネレータ:** Hugo
- **テーマ:** Blowfish
- **言語:** Markdown（コンテンツ）、TOML（設定）
- **CI/CD:** GitHub Actions
- **ホスティング:** GitHub Pages
- **スタイリング:** カスタム CSS（グラデーション・アニメーション）

## 🚀 ローカル開発

### 必要な環境

- Hugo 0.152.2 以上（extended 版推奨）
- Git

### セットアップ

```bash
# リポジトリをクローン
git clone https://github.com/hiyasichuka/my-website.git
cd my-website

# サブモジュールを初期化
git submodule update --init --recursive

# ローカルサーバーを起動
hugo server

# ブラウザで開く
# http://localhost:1313
```

### コンテンツ更新

```bash
# 新しいブランチを作成
git checkout -b feature/add-content

# コンテンツを追加・編集
# content/ ディレクトリ内のファイルを編集

# ローカルで確認
hugo server

# コミット・プッシュ
git add .
git commit -m "Add new content"
git push -u origin feature/add-content

# GitHub で PR を作成 → マージ
# 自動的に GitHub Pages にデプロイされます
```

## 📋 ファイル構成

```
my-website/
├── .github/
│   └── workflows/
│       └── hugo.yml              # GitHub Actions ワークフロー
├── archetypes/
│   └── default.md
├── assets/
│   └── custom.css                # カスタムスタイル
├── config/
│   └── _default/
│       ├── hugo.toml             # サイト設定
│       ├── params.toml           # テーマパラメータ
│       ├── menus.ja.toml         # 日本語メニュー
│       └── menus.en.toml         # 英語メニュー
├── content/
│   ├── _index.md                 # ホームページ
│   ├── projects/
│   │   └── _index.md             # プロジェクトページ
│   └── skills/
│       └── _index.md             # スキルページ
├── docs/
│   └── DEPLOYMENT.md             # デプロイガイド
├── layouts/                       # カスタムレイアウト
├── static/                        # 静的ファイル
├── themes/
│   └── blowfish/                 # Blowfish テーマ
├── hugo.toml
├── go.mod
└── README.md (このファイル)
```

## 🔄 デプロイ

このサイトは GitHub Pages で自動デプロイされます。

**デプロイワークフロー:**

1. `main` ブランチに push
2. GitHub Actions が Hugo でビルド
3. `/public` ディレクトリが GitHub Pages にデプロイ
4. サイトが自動更新

詳細は [docs/DEPLOYMENT.md](docs/DEPLOYMENT.md) を参照してください。

## 📝 更新情報

- **2024/12/13** - ポートフォリオサイト初期公開

## 💡 カスタムドメイン設定

カスタムドメイン `takahashi-kei.dev` を設定する場合：

1. ドメインを取得（Namecheap、Google Domains 等）
2. DNS 設定で GitHub Pages の IP アドレスを指定
3. GitHub Settings → Pages → Custom domain に入力
4. HTTPS を有効化

詳細は [docs/DEPLOYMENT.md](docs/DEPLOYMENT.md#-ドメイン設定カスタムドメイン) を参照。

## 🔧 設定のカスタマイズ

### サイトタイトル・説明

`config/_default/hugo.toml` を編集：

```toml
baseURL = 'https://takahashi-kei.dev/'
languageCode = 'ja'
title = '高橋慶 | Data Engineering Manager'
```

### テーマカラー

`assets/custom.css` を編集：

```css
:root {
  --primary-color: #667eea; /* 紫色 */
  --primary-dark: #764ba2; /* 濃い紫 */
  --accent-color: #f093fb; /* ピンク色 */
}
```

### メニュー

`config/_default/menus.ja.toml` と `config/_default/menus.en.toml` を編集

## 📧 連絡先

ポートフォリオの内容に関するご質問・ご相談は GitHub Issues でお気軽にお問い合わせください。

## 📄 ライセンス

このリポジトリは MIT ライセンスの下で公開されています。

---

**最後更新:** 2024 年 12 月 13 日  
**作成者:** 高橋慶
