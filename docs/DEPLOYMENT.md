# GitHub Pages デプロイガイド

このポートフォリオサイトは GitHub Pages で公開できるように設定されています。

## 📋 セットアップ手順

### ステップ 1: GitHub リポジトリ設定

1. GitHub で [hiyasichuka/my-website](https://github.com/hiyasichuka/my-website) にアクセス
2. **Settings** → **Pages** を開く
3. 以下の設定を確認・変更：

```
Source: GitHub Actions
```

これで自動的に GitHub Actions から `/public` ディレクトリがデプロイされます。

### ステップ 2: PR をマージ

1. [プルリクエスト #1](https://github.com/hiyasichuka/my-website/pull/1) を確認
2. **Merge pull request** をクリック
3. マージ後、自動的に GitHub Actions が実行開始

### ステップ 3: デプロイ確認

1. **Actions** タブを開く
2. `Deploy to GitHub Pages` ワークフローの実行を確認
3. ✅ すべてのジョブが成功したら完了

### ステップ 4: サイトにアクセス

デプロイ完了後、以下の URL でアクセス可能：

```
https://hiyasichuka.github.io/my-website/
```

## 🔧 ドメイン設定（カスタムドメイン）

`https://takahashi-kei.dev/` で公開したい場合：

### オプション A: カスタムドメインを使用

1. GitHub Settings → Pages → **Custom domain** に以下を入力：

   ```
   takahashi-kei.dev
   ```

2. ドメインの DNS 設定で GitHub Pages の IP アドレスを指定：

   ```
   A レコード: 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
   または
   CNAME レコード: hiyasichuka.github.io
   ```

3. DNS 設定が反映されるまで待機（数分～数時間）

4. GitHub Settings → Pages で **Enforce HTTPS** にチェック

### オプション B: デフォルトドメインで公開

カスタムドメイン不要な場合は、GitHub Pages のデフォルトドメインで公開：

```
https://hiyasichuka.github.io/my-website/
```

## 📝 hugo.toml の更新

カスタムドメインを設定する場合は、[hugo.toml](../../hugo.toml) を更新：

**現在:**

```toml
baseURL = 'https://takahashi-kei.dev/'
```

カスタムドメイン未設定の場合は：

```toml
baseURL = 'https://hiyasichuka.github.io/my-website/'
```

## 🔄 自動デプロイの仕組み

このリポジトリは GitHub Actions で自動デプロイが設定されています：

### ワークフロー: `.github/workflows/hugo.yml`

**トリガー:**

- `main` ブランチへの push
- プルリクエスト（プレビュー用）

**ジョブ:**

1. **build** - Hugo でサイトをビルド
2. **deploy** - GitHub Pages にデプロイ

## 🚀 更新フロー

新しいコンテンツを追加する場合：

```bash
# 1. 新しいブランチを作成
git checkout -b feature/add-new-content

# 2. コンテンツを追加・編集
# ...

# 3. ローカルで動作確認
hugo server

# 4. コミット・プッシュ
git add .
git commit -m "Add new content"
git push -u origin feature/add-new-content

# 5. PR を作成（GitHub で）
# 6. PR をマージ
# 7. main ブランチに自動デプロイ
```

## 🔍 トラブルシューティング

### デプロイが失敗する場合

**確認事項:**

- ✅ Hugo バージョンが一致しているか（Hugo 0.152.2+）
- ✅ `.github/workflows/hugo.yml` が正しく設定されているか
- ✅ `hugo.toml` の `baseURL` が正しいか

**ログ確認:**

1. GitHub Actions タブで失敗したワークフローをクリック
2. **build** ジョブのログを確認
3. エラーメッセージから原因を特定

### サイトが表示されない場合

- ✅ GitHub Pages が有効になっているか（Settings → Pages）
- ✅ Source が **GitHub Actions** に設定されているか
- ✅ DNS 設定が反映されているか（カスタムドメイン使用時）

## 📚 参考リンク

- [Hugo 公式ドキュメント - GitHub Pages](https://gohugo.io/hosting-and-deployment/hosting-on-github/)
- [GitHub Pages ドキュメント](https://docs.github.com/en/pages)
- [GitHub Actions ドキュメント](https://docs.github.com/en/actions)
