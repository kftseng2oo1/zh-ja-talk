# 對面說 — 中文 × 日語/韓語 面對面翻譯 PWA

手機放桌上，上半中文、下半日文或韓文（中間切換，旋轉 180°），語音輸入 → Claude 翻譯 → 朗讀。

## 部署
把整個資料夾的檔案放到 GitHub Pages 的任一目錄（例如 `zh-ja-talk/`），瀏覽 `index.html` 即可；
iOS Safari 用「加入主畫面」安裝。

## 檔案
- `index.html` — 全部 UI 與邏輯（ES5，iOS WebView 相容）
- `manifest.json`、`sw.js` — PWA 安裝與離線快取（API 呼叫不快取）
- `icon-192.png`、`icon-512.png`

## 設定
`index.html` 內 `WORKER_URL` 指向 `arcar.kftseng2oo1.workers.dev`（Anthropic messages 代理），`MODEL` 為 `claude-sonnet-4-6`。

## 離線使用
- Service Worker 會把 App 本體快取到手機；安裝到主畫面後，沒網路也開得起來。
- 📖 離線片語本內建 70+ 句常用中／日／韓對照（含讀音），不需網路。
- 有網路時翻譯過的句子會存在手機，離線時同一句可直接重用。
- 自由翻譯與語音辨識需要網路。朗讀要離線可用，請先在 iOS「設定 → 輔助使用 → 朗讀內容 → 聲音」下載日語／韓語語音。
