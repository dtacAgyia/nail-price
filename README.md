**中文** | [English](README.en.md)

# Nail Price Calculator｜美甲價目計算機

一個輕量、行動裝置友善的美甲服務報價計算機。單一 HTML 檔案即可運行，無需安裝、無需建置流程，開啟瀏覽器就能用。

## 功能特色

- **卸甲服務選擇**：本店／他店、純卸甲、卸甲續作、卸甲＋前置保養等多種組合
- **美甲款式報價**：單色、貓眼、鏡面／漸層／法式、簡約款、進階款、複雜款
- **加購項目**
  - 補甲（$50 / 指，可多指累加）
  - 單色換貓眼（+$100，需搭配基本服務）
- **即時總金額計算**，以新台幣 (TWD) 顯示
- **一鍵複製報價單**，自動產生格式化文字明細，方便貼到 LINE 或訊息給客人
- **一鍵重置**所有選項
- **手機 Web App 體驗**：支援 iOS Add to Home Screen（apple-touch-icon、自訂 App 名稱）

## 價目表

### 卸甲服務 Removal
| 項目 | 價格 |
| --- | --- |
| 無需卸甲 | Free |
| 本店卸甲續作 | $100 |
| 他店卸甲續作 | $200 |
| 本店純卸甲（不含前置） | $300 |
| 他店純卸甲（不含前置） | $400 |
| 本店卸甲 + 前置保養 | $500 |

### 美甲款式 Art Design
| 款式 | 價格 | 說明 |
| --- | --- | --- |
| 單色 | $600 | 含前置、建構、保養 |
| 貓眼 | $700 | 含前置、建構、保養 |
| 鏡面／漸層／法式 | $900 | 含前置、建構、保養 |
| 簡約款 | $900 | 簡單線條、飾品點綴 |
| 進階款 | $1000 | 暈染、鏡面粉、少許凹凸 |
| 複雜款 | $1200 | 手繪、大飾品、複合式凹凸 |

### 加購 Add-ons
| 項目 | 價格 |
| --- | --- |
| 補甲 | $50 / 指 |
| 單色換貓眼 | +$100 |

> 純卸甲／卸甲＋前置保養為獨立服務，選取時會自動禁用美甲款式區塊。

## 快速開始

直接於瀏覽器開啟 `index.html` 即可使用：

```bash
git clone https://github.com/dtacAgyia/nail-price.git
cd nail-price
open index.html        # macOS
# 或在 Windows 直接雙擊 index.html
```

或啟用任意靜態伺服器：

```bash
python3 -m http.server 8000
# 然後瀏覽 http://localhost:8000
```

## 技術棧

- **React 18**（透過 CDN UMD 載入）
- **Tailwind CSS**（CDN）
- **Babel Standalone**（瀏覽器端 JSX 編譯）
- 內嵌 Lucide-style SVG icons（無外部 icon 套件依賴）

整個專案是一個 **單一 `index.html`**，沒有 build step、沒有 `node_modules`，方便部署到任何靜態空間（GitHub Pages、Netlify、Vercel、Cloudflare Pages 等）。

## 專案結構

```
nail-price/
├── index.html              # 主程式（React App）
├── apple-touch-icon.png    # iOS 主畫面圖示
└── apple-touch-icon.svg    # 向量版圖示
```

## 部署到 GitHub Pages

1. 進入 repo 的 **Settings → Pages**
2. Source 選擇 `Deploy from a branch`
3. Branch 選 `main`、資料夾選 `/ (root)`
4. 儲存後等待數十秒，即可透過 `https://dtacagyia.github.io/nail-price/` 開啟

## 客製化價目

所有價格皆寫在 `index.html` 中的 `services` 與 `removalOptions` 陣列，例如：

```js
const services = [
  { id: 'single', name: '單色', price: 600, desc: '含前置、建構、保養' },
  // ...
];
```

修改後存檔重新整理瀏覽器即可，無需重新編譯。

## 複製報價範例

按下「複製」後會產生如下格式：

```
【美甲服務報價單】
------------------
■ 本店卸甲續作: $100
■ 單色: $600
■ 加購-單色換貓眼: $100
■ 加購-補甲 (2指): $100
------------------
總金額: $900
```

## License

尚未指定 License。如需開源使用請先與作者確認。
