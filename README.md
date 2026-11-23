# 旅伴手帳（GitHub Pages 版）

這是一個純靜態網站，不需要伺服器。資料存在每個人自己手機（瀏覽器）的本機儲存空間。

## 檔案

| 檔案 | 用途 |
| --- | --- |
| `index.html` | 整個 App |
| `manifest.webmanifest` | 讓它可以「加到主畫面」 |
| `sw.js` | 離線快取，開過一次之後沒網路也能開 |
| `icon-192.png` `icon-512.png` `apple-touch-icon.png` | 主畫面圖示 |

## 上架到 GitHub Pages

1. 在 GitHub 建立一個新的 repository（例如 `travel-companion`）。
2. 把這個資料夾裡的所有檔案，直接放在 repository 的最上層（不要再包一層資料夾），然後 commit。
3. 進入 repository 的 **Settings → Pages**。
4. **Source** 選 *Deploy from a branch*，Branch 選 `main`，資料夾選 `/ (root)`，按 Save。
5. 等一兩分鐘，網址會是 `https://你的帳號.github.io/repository名稱/`。

## 加到手機主畫面

- iPhone：用 Safari 開網址 → 分享按鈕 → 加入主畫面。
- Android：用 Chrome 開網址 → 右上角選單 → 安裝應用程式（或加到主畫面）。

## 備份

資料只存在那支手機的瀏覽器。換手機、清除瀏覽器資料、解除安裝前，請在首頁最下方按「備份資料」存成檔案；之後按「還原資料」匯入。

## 更新 App 之後

如果你改了 `index.html` 並重新上傳，請把 `sw.js` 第一行附近的 `CACHE = 'travel-companion-v1'` 改成 `v2`、`v3`…，各裝置才會抓到新版。
