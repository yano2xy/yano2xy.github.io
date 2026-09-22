# yano2xy.github.io

yano2xy が公開するアプリの案内サイトです。GitHub Pages 上で、各アプリの紹介ページ・プライバシーポリシー・サポートページをまとめて公開することを目的としています。

- HTML / CSS のみで構成された静的サイトです（JavaScript・外部フレームワーク不使用）
- 外部フォント・アクセス解析・Cookie・トラッキング機能は使用していません
- 複数アプリを `apps/` 配下に追加していく構成になっています

## ディレクトリ構成

```text
yano2xy.github.io/
├── index.html                       # トップページ（アプリ一覧）
├── 404.html                         # 404ページ
├── .nojekyll                        # GitHub Pages の Jekyll 処理を無効化
├── README.md
├── assets/
│   └── common.css                   # 全ページ共通スタイル
└── apps/
    └── shokutakucho/
        ├── index.html                # アプリ案内ページ
        ├── privacy/
        │   └── index.html            # プライバシーポリシー
        └── support/
            └── index.html            # サポートページ
```

## 公開URL

| ページ | URL |
| --- | --- |
| トップページ | https://yano2xy.github.io/ |
| shokutakucho 案内ページ | https://yano2xy.github.io/apps/shokutakucho/ |
| shokutakucho プライバシーポリシー | https://yano2xy.github.io/apps/shokutakucho/privacy/ |
| shokutakucho サポート | https://yano2xy.github.io/apps/shokutakucho/support/ |
| 404ページ | https://yano2xy.github.io/404.html |

## 新しいアプリを追加する手順

1. `apps/<アプリ名>/` ディレクトリを作成する
2. その中に `index.html`（アプリ案内ページ）、`privacy/index.html`（プライバシーポリシー）、`support/index.html`（サポートページ）を作成する
   - 既存の `apps/shokutakucho/` 配下のファイルをコピーして、内容を差し替えると作りやすい
   - CSSの参照は `<link rel="stylesheet" href="/assets/common.css">` のようにルートからの絶対パスにする（階層が変わっても正しく読み込まれる）
3. トップページ（`index.html`）の `<ul class="app-list">` 内に `<li class="app-card">` ブロックを追加し、新しいアプリへのリンクを設置する
4. 各ページの `<title>` / `<meta name="description">` / ナビゲーションのリンクを新しいアプリ用に更新する
5. リンク切れがないか、ブラウザで実際に開いて確認する

## GitHub Pages の設定方法

1. GitHubリポジトリの **Settings** → **Pages** を開く
2. **Source** を `Deploy from a branch` に設定する
3. **Branch** を `main`、フォルダを `/(root)` に設定して **Save** する
4. 反映後、`https://yano2xy.github.io/` でサイトが公開される

## 公開前の確認事項

`apps/shokutakucho/` 配下のプライバシーポリシー・サポートページは、開発者から提供された情報（取得する情報、利用目的、外部サービス〈Supabase〉、アクセス権限、退会時のデータ削除、問い合わせ先メールアドレス、制定日など）をもとに記載済みで、仮置き表記（`【要確認】`）は残っていません。実装内容に変更があった場合は、該当ページを更新してください。
