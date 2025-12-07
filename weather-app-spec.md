# 森森天氣 App - 需求規格文件

> **專案名稱**: 森森天氣 (Weather App)
> **版本**: 1.0
> **文件類型**: 需求規格 (REQ)、畫面規格 (UI)、資料規格 (API)
> **適用對象**: 前端開發工程師、UI/UX 設計師、後端 API 開發者

---

## 📋 文件清單

| # | 文件 | 狀態 | 填寫時間 |
|---|------|------|---------|
| 1 | **需求規格** | ✅ 完成 | 45 分鐘 |
| 2 | **畫面規格** | ✅ 完成 | 40 分鐘 |
| 3 | **資料規格** | ✅ 完成 | 35 分鐘 |

---

## 1️⃣ 需求規格 (REQ)

```yaml
id: REQ-WEATHER-001

title: "森森天氣 - 台灣在地化天氣資訊應用"

owner: 課程學員

areas: [Core.UI]                  # 從清單選

goals:                          # 為什麼做？(2-5條)
  - "讓使用者能夠快速查看台灣各地天氣資訊"
  - "提供生活化的天氣建議（帶傘、穿衣）"
  - "提升使用者出門準備的便利性"
  - "打造可愛的台灣在地化天氣體驗"

non_goals:                      # 不做什麼？(1-3條)
  - "不提供國際城市天氣查詢"
  - "不提供詳細的天氣預報數據分析"
  - "不整合第三方天氣服務"

acceptance:                     # 怎樣算完成？(5-10條)
  - "當使用者開啟 App 時，系統應顯示當前位置天氣"
  - "當資料載入時，顯示可愛的 Loading 動畫"
  - "根據降雨機率 > 30% 時，顯示帶傘建議"
  - "根據溫度顯示適當的穿衣建議"
  - "資料載入時間 < 2000ms（含 1.5 秒最低等待時間）"
  - "橫向滑動預報區域應支援 3-7 天預報顯示"
  - "App 應支援台灣主要城市的天氣查詢"
  - "UI 應符合台灣在地化設計風格（可愛、親民）"
  - "錯誤處理：API 失敗時顯示友善的錯誤訊息"
  - "響應式設計：支援手機端瀏覽"

links:
  figma: "https://www.figma.com/design/..."  # 待提供
  demo: "https://weather-app-demo.netlify.app"
```

---

## 2️⃣ 畫面規格 (UI)

```yaml
id: REQ-WEATHER-001-UI

title: "森森天氣 - 畫面佈局與互動設計"

layout:
  type: 單頁應用                    # 單頁面應用
  structure:
    - 載入畫面（全螢幕）
    - 頂部狀態列
    - 主內容區域
      - 今日天氣焦點卡片
      - 稍後預報橫向滑動區

design_system:
  theme: 台灣在地化
  colors:
    - primary: "#7DE1A9"    # 森系綠
    - secondary: "#FFFEF2"  # 奶油白
    - accent: "#F9F195"    # 淡黃
    - text: "#58504A"      # 深棕
  fonts:
    - primary: "Zen Maru Gothic"
    - weights: [400, 700, 900]
  icons: emoji                    # 使用 emoji 作為天氣圖示

zones:
  載入畫面:
    type: 全螢幕覆蓋
    content: 雲朵動畫 + 載入文字
    animation: 雲朵上下彈跳動畫

  狀態列:
    position: sticky-top
    elements:
      - 位置標籤: "📍 新北" (左側)
      - 更新時間: "12月7日 週六" (右側)

  主內容區域:
    padding: 20px
    max_width: 600px
    margin: 0 auto

  今日天氣卡片:
    type: 主焦點卡片
    elements:
      - 時段標籤: 早晨/中午/下午/晚上 (氣泡樣式)
      - 天氣圖示: 大型 emoji (動畫彈跳)
      - 溫度顯示: 大字體粗體
      - 天氣描述: 次標題
      - 建議區域: 2x2 網格
        - 雨傘建議: 圖示 + 文字 + 降雨機率
        - 穿衣建議: 圖示 + 文字 + 最高溫

  預報滑動區:
    type: 橫向滑動容器
    title: "稍後預報"
    cards:
      - type: 小卡片
      - elements:
        - 時段標籤: "明天早晨"等
        - 天氣圖示: 中型 emoji
        - 溫度範圍: "25° - 28°"
        - 降雨機率: "💧30%"

flows:
  主要流程:
    觸發: "開啟網頁"
    流程:
      1. 顯示載入畫面（1.5秒最低等待）
      2. 呼叫天氣 API
      3. 隱藏載入畫面
      4. 渲染主內容
      5. 更新狀態列時間

  資料更新流程:
    觸發: "頁面重新載入"
    流程:
      1. 顯示更新中狀態
      2. 重新獲取資料
      3. 更新所有顯示內容
      4. 更新最後更新時間

interactions:
  - 橫向滑動: 支援觸控滑動預報卡片
  - 載入動畫: 雲朵 emoji 彈跳效果
  - 氣泡效果: 時段標籤輕微傾斜
  - 卡片陰影: 柔和的投影效果

responsive:
  mobile_first: true
  breakpoints:
    - mobile: "max-width: 768px"
    - desktop: "min-width: 769px"
```

---

## 3️⃣ 資料規格 (API)

```yaml
id: REQ-WEATHER-001-API

title: "森森天氣 - 資料來源與處理規格"

天氣資料區塊:
  說明: "從後端 API 獲取台灣各地天氣預報資料"

  主要資料來源:
    服務: WeatherNTP
    方法: GET /api/weather/{city}
    參數:
      - city: "kaohsiung" (目前固定高雄，未來可擴展)
    回傳格式: JSON
    資料結構:
      success: boolean
      data:
        forecasts: array
          - startTime: "2024-12-07T06:00:00Z"
          - endTime: "2024-12-07T18:00:00Z"
          - weather: "多雲時晴"
          - maxTemp: "28"
          - minTemp: "24"
          - rain: "20"

資料處理邏輯:
  當前天氣:
    說明: "取 forecasts[0] 作為當前時段天氣"
    計算:
      - 平均溫度: (maxTemp + minTemp) / 2 四捨五入
      - 時段判斷: 根據 startTime 判斷早晨/中午/下午/晚上
      - 天氣圖示: 根據 weather 文字匹配 emoji

  未來預報:
    說明: "取 forecasts[1:] 作為未來預報"
    處理:
      - 日期判斷: 與今天比較，不同日期加上「明天」前綴
      - 時段標籤: 組合日期 + 時段
      - 顯示格式: "minTemp° - maxTemp°"

  生活建議:
    雨傘建議:
      邏輯: "rain > 30 ? '記得帶傘！' : '不用帶傘'"
      圖示: "rain > 30 ? '☂️' : '🌂'"

    穿衣建議:
      邏輯: |
        if maxTemp >= 28: "短袖出發" 👕
        elif maxTemp <= 20: "加件外套" 🧥
        else: "舒適穿搭" 👕

資料驗證:
  必填欄位:
    - success: 必須為 true
    - forecasts: 至少需有 1 筆資料
    - 每筆 forecast 需包含: startTime, weather, maxTemp, minTemp, rain

  資料型別:
    - maxTemp/minTemp: 字串數字
    - rain: 字串百分比
    - startTime: ISO 8601 格式

錯誤處理:
  API 失敗:
    - 顯示訊息: "天氣資料讀取失敗，狸克把網路線咬斷了！"
    - 保持載入畫面顯示

  資料異常:
    - 天氣文字空白: 預設 "🌤️"
    - 溫度為空: 顯示 "--°"
    - 降雨機率異常: 顯示 "N/A"

快取策略:
  - 不使用快取，每次載入重新獲取
  - 未來可考慮加入 Service Worker 離線快取

待確認:
  - "API 是否支援其他台灣城市？目前只看到 kaohsiung"
  - "天氣文字分類是否完整？需要確認所有可能的 weather 值"
  - "API 的更新頻率和資料準確性"
```

---

## ⚠️ 技術限制與注意事項

### 效能考量
- 載入時間控制在 2 秒內（含 1.5 秒動畫等待）
- 使用 Promise.all 同時處理延遲和 API 呼叫
- 圖片資源使用 emoji，避免額外載入

### 瀏覽器相容性
- 支援現代瀏覽器（Chrome, Firefox, Safari, Edge）
- 使用 CSS Grid 和 Flexbox
- 相容性問題：iOS 左右滑動防止

### 無障礙考量
- 使用語意化 HTML 結構
- 顏色對比度符合 WCAG 標準
- 支援鍵盤導航（未來可擴展）

---

## 📁 專案結構

```
weather-app/
├── index.html              # 主應用程式
├── icon-v2.png            # App 圖示
├── docs/
│   ├── weather-app-spec.md # 本規格文件
│   └── requirements/       # 相關需求文件
└── README.md              # 專案說明
```

---

## 🔄 後續開發建議

### Phase 2 功能擴展
- [ ] 支援選擇不同台灣城市
- [ ] 新增 7 天詳細預報
- [ ] 加入天氣警告通知
- [ ] 新增收藏城市功能

### 技術優化
- [ ] 加入 Service Worker 離線支援
- [ ] 優化載入效能
- [ ] 加入錯誤重試機制
- [ ] 新增資料快取策略

---

## 📞 聯絡與支援

- **技術問題**: 前端工程師協助
- **API 規格**: 後端開發團隊
- **設計問題**: UI/UX 設計師
- **產品需求**: PM 或課程講師

---

*本文件遵循 SDD (Software Design Document) 標準格式，參考 PM 文件提供指南 v1.0*
