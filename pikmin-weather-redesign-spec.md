# 🥕 皮克敏氣象站 - 風格改造規格文件

> **原始專案**: 森森天氣 (Weather App)
> **新風格**: 皮克敏 (Pikmin) 風格
> **目標**: 打造可愛、有機感的天氣資訊體驗

---

## 🎯 改造目標

將原本的「森森天氣」轉型為充滿生命力的「皮克敏」風格氣象站，強調：
- **可愛的擬人化設計**：讓天氣資訊像活生生的皮克敏一樣
- **遊戲化體驗**：互動感強，充滿驚喜
- **自然有機感**：植物、泥土、陽光等自然元素
- **鮮豔色彩**：皮克敏系列的經典色調

---

## 📋 風格改造清單

| # | 改造項目 | 狀態 | 難度 | 預估時間 |
|---|---------|------|------|---------|
| 1 | **名稱與品牌** | ⏳ 待確認 | ⭐ | 15 分鐘 |
| 2 | **視覺設計系統** | ⏳ 待確認 | ⭐⭐ | 45 分鐘 |
| 3 | **Icon 與插圖** | ⏳ 待確認 | ⭐⭐⭐ | 60 分鐘 |
| 4 | **文案與互動** | ⏳ 待確認 | ⭐ | 30 分鐘 |

---

## 🏷️ 1. 名稱與品牌改造

### 建議名稱選項

```yaml
brand_options:
  - name: "皮克敏天氣站"
    tagline: "召喚你的天氣小幫手！"
    concept: "直接使用皮克敏IP，強調召喚的概念"

  - name: "小葉氣象"
    tagline: "葉子們的氣象報告"
    concept: "葉子代表皮克敏，輕鬆可愛"

  - name: "萌芽天氣"
    tagline: "讓天氣資訊萌芽綻放"
    concept: "強調生長、萌芽的植物意象"

  - name: "阿豪報氣象"
    tagline: "皮克敏風格的天氣播報"
    concept: "個人化品牌名稱（你的建議）"
```

### 🎨 品牌色彩
```yaml
primary_colors:
  - pikmin_red: "#FF6B6B"      # 紅色皮克敏
  - pikmin_blue: "#4ECDC4"     # 藍色皮克敏
  - pikmin_yellow: "#FFE66D"   # 黃色皮克敏
  - soil_brown: "#8B4513"      # 泥土色
  - leaf_green: "#7CB342"      # 葉子綠
  - sky_blue: "#87CEEB"        # 天空藍
```

---

## 🎨 2. 視覺設計系統

### 整體風格定義
```yaml
design_system:
  theme: "皮克敏冒險風"
  style: "可愛擬人化"
  inspiration: "植物生命 + 遊戲互動"

  visual_elements:
    - rounded_corners: "大量使用圓角設計"
    - organic_shapes: "有機形狀，避免直角"
    - playful_animations: "輕快彈跳動畫"
    - layered_depth: "多層次視覺深度"
```

### 色彩配置
```yaml
color_palette:
  background: "#FFF8E1"    # 溫暖的米色背景
  primary: "#7CB342"      # 葉子綠作為主色
  secondary: "#FFE66D"    # 太陽黃
  accent: "#FF6B6B"       # 活力紅
  text: "#2E2E2E"         # 深色文字
  borders: "#D4E157"      # 淺綠色邊框
```

### 字體與排版
```yaml
typography:
  primary_font: "Zen Maru Gothic"  # 保持現有字體
  display_font: "手寫風字體"      # 用於標題（如果有）
  sizes:
    hero_temp: "5rem"      # 溫度數字
    section_title: "1.5rem" # 區塊標題
    card_text: "1rem"      # 卡片內容
  weights: [400, 700, 900]
```

---

## 🌟 3. Icon 與插圖設計

### 天氣圖示重新設計
```yaml
weather_icons_redesign:
  sunny: "☀️ → 🌻"        # 太陽改為向日葵
  cloudy: "☁️ → ☁️"       # 雲朵保持但加上葉子裝飾
  rainy: "🌧️ → 💧"        # 雨滴更可愛
  thunder: "⛈️ → ⚡"       # 閃電保持但風格化
  default: "🌤️ → 🌱"      # 預設改為小芽苗

pikmin_character_icons:
  red_pikmin: "🔴"        # 力量型，代表高溫
  blue_pikmin: "🔵"       # 防水型，代表雨天
  yellow_pikmin: "🟡"      # 飛行型，代表晴天
  captain: "👨‍🚀"         # 隊長，代表使用者
```

### 主畫面佈局調整
```yaml
hero_section_redesign:
  background_pattern: "葉子與花瓣點綴"
  main_icon: "皮克敏隊長 + 天氣元素"
  layout: "更圓潤的卡片設計"
  animations: "輕輕搖曳的葉子動畫"
```

### 建議區域重新設計
```yaml
advice_section_redesign:
  umbrella_advice:
    icon: "🌂 → 🛡️"       # 雨傘改為盾牌（皮克敏風）
    text: "不用帶傘 → 放心出門啦！"
    concept: "像皮克敏一樣無憂無慮"

  clothing_advice:
    icon: "👕 → 👔"        # 服裝改為更可愛的風格
    text: "舒適穿搭 → 輕鬆上陣！"
    concept: "準備好冒險的心情"
```

---

## 💬 4. 文案與互動改造

### 主要文案調整
```yaml
text_content_update:
  app_title: "森森天氣 → 皮克敏天氣站"
  loading_text: "正在觀測雲的流動... → 召喚皮克敏小隊..."
  location_label: "📍 新北 → 🌱 新北冒險基地"
  error_message: "狸克把網路線咬斷了！ → 皮克敏們迷路了，請檢查網路！"

  advice_suggestions:
    rain_high: "記得帶傘！ → 組隊冒險，注意雨天！"
    rain_low: "不用帶傘 → 放心出門啦！"
    hot_weather: "短袖出發 → 炎熱挑戰，保持水分！"
    cold_weather: "加件外套 → 寒冷任務，穿暖一點！"
    normal_weather: "舒適穿搭 → 完美天氣，輕鬆上陣！"
```

### 互動體驗升級
```yaml
interaction_improvements:
  loading_animation: "雲朵彈跳 → 皮克敏召喚動畫"
  card_hover: "輕微陰影 → 葉子輕輕搖曳"
  temperature_display: "數字顯示 → 加上可愛的表情符號"
  forecast_cards: "橫向滑動 → 像皮克敏隊伍一樣排列"

  sound_effects: "建議"
    - click_sounds: "可愛的葉子聲音"
    - weather_change: "天氣轉換的輕快音效"
```

---

## 🎮 遊戲化元素

### 皮克敏主題特色
```yaml
pikmin_features:
  - character_assignment: "根據天氣類型顯示不同顏色皮克敏"
  - team_concept: "將預報視為『小隊任務』"
  - growth_metaphor: "天氣改善像皮克敏成長"
  - exploration_feeling: "瀏覽預報像探索新大陸"
```

### 互動強化
```yaml
enhanced_interactions:
  - tap_animations: "點擊卡片有輕微反饋動畫"
  - weather_transitions: "天氣轉換有平滑過渡效果"
  - character_reactions: "不同天氣下皮克敏有不同表情"
  - achievement_system: "可選：連續查看天氣解鎖小成就"
```

---

## 📱 保持的原有功能

### ✅ 不變的功能
- API 端點維持：`https://weather-ntp.zeabur.app/api/weather/kaohsiung`
- 資料處理邏輯完全相同
- 響應式設計架構
- 效能優化策略

### 🔄 調整的功能
- 視覺表現完全重設計
- 文案全部本地化
- Icon 系統全面更換
- 動畫效果優化

---

## 🎯 實施建議

### Phase 1: 核心風格改造 (2-3 小時)
1. 更新色彩變數
2. 更換主要 icon
3. 調整文案內容
4. 修改基本樣式

### Phase 2: 進階互動優化 (2-3 小時)
1. 新增皮克敏主題動畫
2. 優化互動效果
3. 加入聲音回饋
4. 測試整體體驗

### Phase 3: 細節完善 (1-2 小時)
1. 微調色彩平衡
2. 優化載入體驗
3. 加入小彩蛋

---

## ❓ 確認事項

在開始實作前，請確認：

1. **品牌名稱**：你想要使用哪個名稱？
2. **色彩偏好**：是否需要調整建議的色彩配置？
3. **Icon 風格**：偏好哪種程度的擬人化設計？
4. **互動強度**：希望增加多少遊戲化元素？

---

*請確認以上規格後，我將開始進行程式碼改造！*
