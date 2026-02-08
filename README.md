# 數學大冒險 PWA

## 檔案結構

```
數學大冒險-pwa/
├── index.html      ← 遊戲本體
├── sw.js           ← Service Worker（離線快取）
├── manifest.json   ← PWA 設定檔
├── icon-192.png    ← App 圖示
├── icon-512.png    ← App 圖示（高解析度）
└── README.md       ← 本文件
```

## 部署到 GitHub Pages（免費）

### 第一次設定

1. 在 GitHub 建立新 Repository
   - 到 https://github.com/new
   - 名稱例如 `math-adventure`
   - 設為 Public
   - 點 Create repository

2. 上傳檔案
   ```bash
   cd 數學大冒險-pwa
   git init
   git add .
   git commit -m "初版"
   git branch -M main
   git remote add origin https://github.com/你的帳號/math-adventure.git
   git push -u origin main
   ```

3. 啟用 GitHub Pages
   - 到 Repository → Settings → Pages
   - Source 選 「Deploy from a branch」
   - Branch 選 `main`，資料夾選 `/ (root)`
   - 點 Save

4. 等 1-2 分鐘，你的遊戲就上線了：
   **https://你的帳號.github.io/math-adventure/**

### 更新版本

修改檔案後：
```bash
git add .
git commit -m "更新內容"
git push
```

如果遊戲內容有改（index.html），記得也更新 sw.js 裡的版本號：
```javascript
const CACHE_NAME = 'math-adventure-v2';  // v1 改成 v2
```

## 使用者體驗

### 手機使用者
1. 收到連結，用瀏覽器打開
2. 直接就能玩（不需安裝）
3. 可選：點瀏覽器的「加到主畫面」→ 之後像 App 一樣全螢幕開啟

### 加到主畫面的方法
- **iPhone Safari**：點分享按鈕 → 「加入主畫面」
- **Android Chrome**：點右上角 ⋮ →「加到主畫面」或「安裝應用程式」

加到主畫面後：
- 有自己的圖示
- 全螢幕顯示（沒有瀏覽器框）
- 離線也能玩
- 排行榜紀錄保留在裝置上

## 注意事項

- 排行榜使用 localStorage，資料存在本機
- App 首次載入需要網路，之後離線可用
- 更新遊戲後，使用者下次開啟時會自動更新
- 不需要任何費用，不需要審核
