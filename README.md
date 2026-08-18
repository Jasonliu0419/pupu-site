# PuPu 公開頁面

App Store Connect 的兩個必填 URL 由這個 repo 提供：

- **Support URL** — `https://<owner>.github.io/<repo>/`
- **Privacy Policy URL** — `https://<owner>.github.io/<repo>/privacy.html`

## ⚠️ 不要手動編輯這裡的 HTML

`index.html` 與 `privacy.html` 都是**產生物**。唯一來源是私有 repo
`Jasonliu0419/PuPu-App` 的 `constants/legal.json`，由 `scripts/gen-privacy-site.mjs` 產生。

手改這裡會讓 app 內顯示的政策與公開版漂移 —— 後果是「使用者在 app 裡讀到的」跟
「Apple 審核時讀到的」不一致。

## 要改政策文字

1. 在 PuPu-App 改 `constants/legal.json`（app 內頁面會自動跟著變）
2. 跑 `node scripts/gen-privacy-site.mjs <這個 repo 的本機路徑>`
3. 在這個 repo commit 並 push —— GitHub Pages 會自動重新部署
