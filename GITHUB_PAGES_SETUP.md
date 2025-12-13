# GitHub Pages 公開手順

## ✅ 完了した設定

GitHub Pages でのデプロイに必要な以下の設定は完了しています：

- ✅ GitHub Actions ワークフロー (`.github/workflows/hugo.yml`)
- ✅ Hugo ビルド設定
- ✅ デプロイドキュメント
- ✅ README

## 📋 次のステップ（手動設定が必要）

### ステップ 1: GitHub リポジトリ設定

1. **GitHub にアクセス**

   - https://github.com/hiyasichuka/my-website

2. **Settings を開く**

   - リポジトリページ右上の **Settings** をクリック

3. **Pages を選択**

   - 左サイドメニューから **Pages** を選択

4. **Build and deployment の設定**
   ```
   Source: GitHub Actions を選択
   ```

![GitHub Pages Settings](./github-pages-settings.png)

### ステップ 2: PR をマージ

1. **プルリクエストを確認**

   - https://github.com/hiyasichuka/my-website/pull/1

2. **内容を確認**

   - コミット履歴とファイル変更を確認

3. **Merge pull request をクリック**
   - `main` ブランチにマージされます

### ステップ 3: デプロイ確認

1. **Actions タブを開く**

   - https://github.com/hiyasichuka/my-website/actions

2. **Deploy to GitHub Pages を確認**

   - ワークフローが自動実行されます
   - build → deploy の順で実行されます

3. **✅ すべてのジョブが完了するまで待つ**
   - 約 1 ～ 2 分で完了します

### ステップ 4: サイトにアクセス

デプロイ完了後、以下の URL でサイトが公開されます：

```
https://hiyasichuka.github.io/my-website/
```

## 🌐 カスタムドメインの設定（オプション）

`https://takahashi-kei.dev/` で公開したい場合：

### 1. ドメインを取得

- Namecheap
- Google Domains
- お名前.com
  など

### 2. GitHub Pages にカスタムドメインを設定

1. Settings → Pages
2. **Custom domain** に以下を入力：
   ```
   takahashi-kei.dev
   ```
3. **Save** をクリック

### 3. DNS 設定

ドメイン管理画面で DNS レコードを設定：

**オプション A: A レコード（推奨）**

```
ホスト名: @ (または空)
タイプ: A
値:
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

**オプション B: CNAME レコード**

```
ホスト名: www
タイプ: CNAME
値: hiyasichuka.github.io
```

### 4. HTTPS を有効化

1. Settings → Pages
2. **Enforce HTTPS** にチェック
3. DNS 設定が反映されるまで待つ（数分～数時間）

## 📊 デプロイ状況の監視

### GitHub Actions での監視

1. **Actions** タブを開く
2. **Deploy to GitHub Pages** ワークフローをクリック
3. ログを確認

**ステータス:**

- 🟢 成功（Success）- サイト公開中
- 🟡 実行中（In progress）- デプロイ処理中
- 🔴 失敗（Failed）- エラーが発生

### 自動デプロイの仕組み

```
main ブランチに push
     ↓
GitHub Actions トリガー
     ↓
Hugo でビルド (/public を生成)
     ↓
GitHub Pages にデプロイ
     ↓
サイト公開
```

## 🔍 トラブルシューティング

### デプロイが失敗する場合

**1. ワークフロー設定を確認**

```bash
# ローカルで確認
cat .github/workflows/hugo.yml
```

**2. Hugo バージョンを確認**

```bash
hugo version
# 0.152.2 以上であることを確認
```

**3. ビルドが成功するか確認**

```bash
hugo --minify
```

### サイトが表示されない場合

**確認項目:**

- ✅ GitHub Pages が有効か
- ✅ Source が GitHub Actions に設定されているか
- ✅ Actions ワークフローが成功しているか
- ✅ DNS 設定が反映されているか（カスタムドメイン使用時）

### キャッシュのクリア

ブラウザキャッシュをクリア：

- Ctrl + Shift + Delete（Windows）
- Cmd + Shift + Delete（Mac）

## 📚 参考リンク

- [Hugo - Hosting on GitHub](https://gohugo.io/hosting-and-deployment/hosting-on-github/)
- [GitHub Pages Docs](https://docs.github.com/en/pages)
- [GitHub Actions Docs](https://docs.github.com/en/actions)

---

**完了したら、サイトへのアクセスをお知らせください！** 🚀

サイト URL: `https://hiyasichuka.github.io/my-website/`
