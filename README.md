# WorkHoli 法的文書（公開ホスティング用）

ストア審査では **プライバシーポリシーの公開URL** が必須です。このフォルダの静的HTML
（`privacy.html` / `terms.html` / `index.html`）を、ビルド不要でそのまま任意の静的ホストに置けます。
日英併記済み。連絡先メール（doshincreator.ai@gmail.com）入り。

## 一番かんたん：GitHub Pages（無料）

1. GitHub に新規リポジトリ（例：`workholi-legal`）を作成し public にする。
2. このフォルダの3ファイルをリポジトリ直下に push。
   ```
   git init
   git add privacy.html terms.html index.html
   git commit -m "Add WorkHoli legal pages"
   git branch -M main
   git remote add origin https://github.com/<あなた>/workholi-legal.git
   git push -u origin main
   ```
3. リポジトリ Settings → Pages → Build and deployment → Source: **Deploy from a branch**、
   Branch: `main` / `/ (root)` → Save。
4. 数分後に公開URLが発行されます：
   - プライバシー：`https://<あなた>.github.io/workholi-legal/privacy.html`
   - 利用規約　　：`https://<あなた>.github.io/workholi-legal/terms.html`

> 代替：Netlify / Cloudflare Pages / Vercel にフォルダをドラッグ＆ドロップでも可。

## 発行後にやること

- **App Store Connect**：App情報 → プライバシーポリシーURL に privacy.html のURLを入力。
- **Google Play Console**：ポリシー → アプリのコンテンツ → プライバシーポリシー にURLを入力。
- （任意）アプリ内 `app/privacy.tsx` / `app/terms.tsx` は現状アプリ内表示。公開URLへ
  リンクしたい場合は、その画面に「ブラウザで開く」ボタン（`Linking.openURL(URL)`）を足せます。
  審査自体は上記ストア側のURL入力で満たせるため必須ではありません。

## 更新時の注意

文面を変えたら、アプリ内（`app/privacy.tsx` / `app/terms.tsx`）と
このHTMLの**両方**を更新し、`最終更新日 / Last updated` を合わせること。
