# 旅伴手帳（GitHub Pages 版）

## 部署
1. 建立 GitHub repo，把 `index.html` 放在根目錄（`firestore.rules`、`README.md` 可一起放）。
2. Settings → Pages → Source 選 `Deploy from a branch`，Branch 選 `main` / `(root)`。
3. 網址：`https://<帳號>.github.io/<repo>/`

## 模式
- **本機模式（預設）**：不用設定，資料存在瀏覽器 localStorage，只有自己用。
- **多人同步模式**：設定 Firebase（免費 Spark 方案夠用）
  1. https://console.firebase.google.com 建立專案
  2. Build → Authentication → Sign-in method → 啟用「匿名」
  3. Build → Firestore Database → 建立資料庫，Rules 貼上 `firestore.rules` 的內容並發布
  4. 專案設定 → 一般 → 新增網頁應用程式，複製 `firebaseConfig`
  5. 貼到 `index.html` 最上方的 `const FIREBASE_CONFIG = null;`
  6. Authentication → Settings → Authorized domains 加入 `<帳號>.github.io`

## 注意
- Firebase 的 apiKey 放在前端是正常的，安全性靠 Rules。
- 身分是瀏覽器匿名帳號：清除網站資料或換瀏覽器會變成新身分（可用房間代碼重新加入，並選「我是誰」）。
- 房間代碼只是前端的簡單門檻，不是嚴格的存取控制；請勿記錄敏感資料。
