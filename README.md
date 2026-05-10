# Account Manager — Legal Documents

このフォルダには、アプリのプライバシーポリシーと利用規約のHTMLファイルが含まれています。
GitHub Pages で公開してGoogle Play Console に登録するURLとして使うことを想定しています。

## ファイル構成

```
docs/
├── index.html      # ランディングページ（プライバシーと利用規約へのリンク）
├── privacy.html    # プライバシーポリシー（日英）
├── terms.html      # 利用規約（日英）
└── README.md       # このファイル
```

## プレースホルダの差し替え

以下のプレースホルダを実際の値に置き換えてください：

| プレースホルダ | 例 |
|---|---|
| `[DEVELOPER_NAME]` | Mike Stanton |
| `[CONTACT_EMAIL]` | mikestanton.contact@gmail.com |

3ファイル（index.html / privacy.html / terms.html）すべてに含まれているので、エディタの「すべて置換」機能で一括変更が楽です。

## GitHub Pages で公開する手順

### 前提
- GitHubアカウント（無料）

### 手順

1. **GitHub上でリポジトリを作成**  
   公開可能なPublicリポジトリで作成（例：`account-manager-legal`）。

2. **このdocsフォルダの中身をリポジトリにpush**  
   ```powershell
   cd C:\AppProj\app\account_manager\docs
   git init
   git add .
   git commit -m "Add legal documents"
   git branch -M main
   git remote add origin https://github.com/MikeStanton27-proj/account-manager-legal.git
   git push -u origin main
   ```

3. **GitHub Pagesを有効化**  
   - リポジトリの「Settings」→「Pages」を開く
   - Source: 「Deploy from a branch」
   - Branch: `main` / `/ (root)`
   - Save

4. **数分待つと公開URL生成**  
   `https://MikeStanton27-proj.github.io/account-manager-legal/`

5. **動作確認**  
   - `https://MikeStanton27-proj.github.io/account-manager-legal/` → index.html
   - `https://MikeStanton27-proj.github.io/account-manager-legal/privacy.html` → プライバシー
   - `https://MikeStanton27-proj.github.io/account-manager-legal/terms.html` → 利用規約

6. **Google Play Console に登録**  
   - 「アプリのコンテンツ」→「プライバシーポリシー」に  
     `https://MikeStanton27-proj.github.io/account-manager-legal/privacy.html` を入力

## 代替の公開方法

GitHub Pages以外の選択肢：

| 方法 | 無料枠 | 難易度 |
|---|---|---|
| **GitHub Pages** | 完全無料、独自ドメイン可 | 易 |
| **Netlify** | 無料、独自ドメイン可 | 易 |
| **Vercel** | 無料、独自ドメイン可 | 易 |
| **Notion 公開ページ** | 無料、ドラッグ&ドロップ | 最易（HTMLでなくページ作成） |
| **独自サーバー** | 月額 数百円〜 | 中 |

## 更新時のフロー

ポリシーや規約を更新した場合：

1. HTMLファイルの `最終更新日` を新しい日付に変更
2. 該当箇所を編集
3. `git add . && git commit -m "Update privacy" && git push`
4. 数分待つと自動反映

ユーザーへの通知（任意）：アプリ内に「重要なお知らせ」のような形で更新を伝えるのが望ましいです。

## 注意

- これらの文書は **テンプレート** です。本格運用する場合は、必要に応じて弁護士のレビューを受けてください。
- 特に「準拠法」「専属的合意管轄」の項目は、対象市場により調整が必要な場合があります（日本国内向けで作成しています）。
