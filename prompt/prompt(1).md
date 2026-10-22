

## 階段一：專案生成核心任務提示詞 (19:10)

```markdown
【通用任務指令：製作高效能、極速載入且具備細緻點擊回饋的「原理 3D/向量動畫」Web 單頁應用】

請根據以下技術規範與規格，製作指定原理的互動 Web + SVG 動畫應用程式：

1. 模組 1：多媒體輕量化 (Payload Optimization)
   - 優先使用純 SVG 節點與幾何向量描繪，杜絕不必要的重量級外部圖片。
   - 若需點陣背景，必須撰寫 <picture> 標籤支援現代 AVIF / WebP 格式，並搭配 srcset 適配不同螢幕解析度 (1x / 2x / 3x)，確保加載節省率達 80% 以上。

2. 模組 2：SVG 圖示與路徑動畫 (Stroke Dashoffset 動畫技術)
   - 繪製具備 stroke-dasharray 與 stroke-dashoffset 原理的路徑動畫。
   - 關鍵互動按鈕（如：截圖儲存、收藏星標、完成勾選等），撰寫 CSS @keyframes 達成描邊勾勒 (Stroke Drawing) 與填色彈跳 (Bounce) 的微互動。

3. 模組 3：微互動音訊回饋與 60fps 動態調校 (Audio & Motion Tuning)
   - 採用原生 Web Audio API 合成輕脆點擊 (Click)、吸附 (Snap)、成功 (Chord) 互動音效，零外部音檔依賴，杜絕載入延遲。
   - 精確配置 CSS transition / transform 緩動曲線，預設採用極致彈跳 cubic-bezier(0.34, 1.56, 0.64, 1)。
   - 動畫迴圈使用 requestAnimationFrame 保持在 60 FPS，禁止使用耗能的 layout-thrashing 屬性。

4. 互動設計要求：
   - 具備播放/暫停、時間軸滑桿 (Scrubber)、3D 透視視角切換 (Isometric / Perspective 3D)。
   - 提供直覺的深色科技感主題 (Dark Theme)，代碼以單一檔案完整封裝。

【指定主題】：颱風對台灣的影響：原理 3D / 向量互動視覺化工作台
```

---

## 階段二：成果審查與核心學習指標提示詞 (19:22)

```markdown
以這個檔案檢查 index.html ，並指出所有學習方向：

# 人工智慧時代的多媒體網頁設計：學習指標與 AI 產出檢核指南

本指南整合了核心學習指標，以及利用生成式 AI 產出互動網頁或多媒體元件時必備的參數檢核清單。

---

## 一、 學生核心學習指標（Learning Indicators）

所學到的並非生硬的代碼編寫，而是「工程效能與感官體驗的量化標準」：

### 1. 多媒體資源瘦身指標
* 載入等待黃金門檻：理解網頁載入若超過 3 秒，將流失超過 53% 的行動端使用者。
* 傳輸體積節省率：能運用次世代格式（AVIF/WebP）取代傳統 JPEG/PNG，達成節省約 70% 網路傳輸量的目標；透過 SVGO 精簡 SVG 程式碼，消除編輯器垃圾中繼資料，體積立減 60% 以上。
* 響應式載入配置：掌握 <picture>、srcset、sizes 依螢幕解析度智慧分流圖片，以及首屏以外使用 loading="lazy" 原生延遲載入不佔頻寬。

### 2. 動態渲染與流暢度指標
* 60fps（幀率）與運算極限：理解瀏覽器每一影格（Frame）只有 16.6 毫秒 的計算極限。若運算超時會產生肉眼可辨的卡頓與掉幀（Jank）。
* GPU 硬體加速：掌握渲染三階段（重排 Reflow、重繪 Repaint、合成 Composite），明白動畫應鎖定在合成圖層的 transform 與 opacity，做到零重排消耗。
* 感知等待心理學：理解骨架屏（Skeleton Screen）相比傳統 Spinner 轉圈能將心理等待預期縮短約 40%。

### 3. 微互動與多感官回饋指標
* 狀態反饋微動效：按鈕在 :hover（縮放微浮 1.03 倍）與 :active（下沉 0.97 倍）的機械手感設定。
* 路徑動畫掌控：理解 SVG viewBox 座標邏輯，並用 stroke-dasharray 與 stroke-dashoffset 做出 0% 到 100% 的向量描邊勾勒。
* 微音效規格：音效長度需控制在 50～150ms、檔案小於 5KB（Opus/AAC 格式），且利用非同步/實體分離機制達成連續點擊不中斷發聲。

---

## 二、 請 AI 製作出成果後，要檢查哪些「關鍵參數」？

當請 AI 產生網頁元件、CSS 動畫或多媒體代碼時，學生作為「設計把關者」，應檢核以下具體參數：

| 檢核維度 | 核心參數 / 語法項目 | 正確標準（驗收檢查點） | 簡報對應章節 |
| :--- | :--- | :--- | :--- |
| 圖片宣告 | <picture> 標籤語法 | 檢查是否有按照順序提供 <source type="image/avif"> -> <source type="image/webp"> -> <img> 後備格式。 
| 延遲載入 | loading 屬性 | 檢查首屏以外的圖片是否確實標註 loading="lazy"。 
| 向量畫布 | viewBox="X Y W H" | 檢查是否有設定相對座標比例尺（例如 viewBox="0 0 100 100"），且已去除軟體匯出的冗餘中繼資料。 
| 路徑描邊動態 | @keyframes 數值 | 檢查動畫關鍵影格是否有將 stroke-dashoffset 從總長度數值過渡歸零（如 100 -> 0）。 
| 動畫屬性安全 | CSS 操控屬性 | 嚴格檢查動畫是否只使用 transform（平移/縮放/旋轉）與 opacity，絕對避免使用 top、left、width、height（會引發嚴重 Reflow 掉幀）。
| 物理回彈曲線 | transition-timing-function | 避免使用機械死板的 linear，檢查是否採用 ease-out 或自訂四個控制點的 cubic-bezier(x1, y1, x2, y2) 產生擬真彈力。 
| 音效規格 | 音訊時長與容量 | 檢查 AI 挑選或產生的音效檔案時長是否在 50~150ms 內、體積是否控制在 5KB 左右。
| 瀏覽器效能面板 | DevTools Performance | 執行點擊或滾動時，影格耗時是否均在 16.6ms 以內，維持 60fps 零掉幀。 
```
