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
