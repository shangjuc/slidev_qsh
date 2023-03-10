---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
# page transition
transition: slide-left
# use UnoCSS
css: unocss
colorSchema: dark
---

# QSearch 前端工作目標
2023年度及季度目標

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Start<carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/shangjuc" target="_blank" alt="GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--

-->


---
layout: intro
---

# 寫在年度目標之前
產品課題與未來方向

---

# 產品課題：以Trend為例
以我們公司的主力產品Trend來說，目前有以下課題：
1. 系統穩定性
2. 客戶黏著性
3. 產品競爭力


---

# 產品短期目標：框架升級、情境分析
以新框架重構情境分析介面，能夠對應前述三大課題：系統穩定性、客戶黏著性、產品競爭力

1. 提升系統穩定性：
   - 將查詢內容限制在某一範圍，讓後端就此範圍的資料進行快取、主動偵錯；
   - 前端採用新框架及狀態管理架構，讓單元測試成為可能；
2. 提升客戶黏著性：
   - 可以讓客戶一次設定、反覆觀看，滿足客戶日常的監看需求；
   - 搭配權限管理(BAM)，可以讓情境模版由使用者選擇是否共享（共同維護使用）；
3. 提升產品競爭力：
   - 強化既有Trend跨渠道語法自由度和細緻度，維持相比於其他競品的優勢
   - 借鑑Looker Studio(原Google Data Studio)模版的優點，產製更貼合我方資料格式的客製化儀表版


---


# 產品長期目標：持續整合、強化各功能
長遠來看，應該持續整合並強化產品功能，提供更佳的使用者體驗(客戶黏著性)，服務更多類型的客戶(產品競爭力)

1. 熱門文章結合風向分析功能、搭配新版圖表
   - 目前Trend只有FB單一渠道風向分析功能，我們可以先重構熱門文章儀表板，讓使用者在同一介面上直接tag文章，即可結合風向分析功能
   - 搭配更好看的嵌入式儀表板，讓風向分析功能更有升級感

2. 重構Trend既有儀表板、搭配BAM權限控管
   - 重構Trend既有儀表板(ex.熱門關鍵字、文字雲)為嵌入式儀表板，搭配權限控管，將其放在官網上或Looker Studio(原Google Data Studio)，以接觸更多潛在客戶
   - 權限控制也能套用在快訊通知頁面的分享上，讓客戶服務其客戶時，更能彰顯其專業

3. 以新框架重構各功能、加上單元測試，提升系統穩定度




---
layout: intro
---
# 前端年度目標-實作面


---
layout: 
---
# 前端年度目標-2023年
時間： 2023年3月～12月31日

1. Trend++ 前端框架升級
   - Trend 情境分析介面+跨渠道語法編輯器
   - Trend 熱門文章+風向分析功能
   - Trend 嵌入式儀表板(文字雲, 熱度圖, 熱門關鍵字)
2. Trend+ 維運
   - 嵌入Trend++儀表板至既有介面、串接新版API
   - 用新版功能取代舊有模組(ex.風向分析、熱門關鍵字)
3. BAM 維運
4. Pickol 維運
5. 其他：協助招募前端工程師、前端技術分享、因應客戶需求調整每季開發項目



---
layout: intro
---
# 前端季度目標-Q2～Q4



---
layout: 
---
# 前端季度目標-Q2
時間： 2023年3月～6月30日


1. Trend++ 情境分析介面+跨渠道語法編輯器
   - 以新框架開發情境分析介面+跨渠道語法編輯器
   - 與後端協作儲存情境的API串接
2. Trend+ 跨渠道語法API串接+加入新版儲存情境
   - 從Trend++而來的跨渠道語法必須能被正確讀取及渲染
   - 串接新版儲存情境API
3. BAM 加入Trend++使用者權限控管
4. Pickol 交接
   - 交接Pickol前端程式碼
   - 制定開發維運分工流程
5. 其他：協助招募前端工程師、前端技術分享、因應客戶需求調整開發項目




---
layout: 
---
# 前端季度目標-Q3
時間： 2023年7月1日～9月30日

1. Trend++ 熱門文章+風向分析功能
   - 以新框架重構熱門文章 + 整合風向分析功能
   - 與後端協作風向分析的API串接
2. Trend+ 加入新版熱門文章+風向分析
   - 將新版熱門文章嵌入Trend分析介面，供使用者切換使用
   - 用新版熱門文章+風向分析功能取代舊版模組
3. BAM 維運
4. Pickol 維運
5. 其他：檢驗前端團隊分工流程、前端技術分享、因應客戶需求調整開發項目

   



---
layout: 
---
# 前端季度目標-Q4
時間： 2023年10月1日～12月31日

1. Trend++ 嵌入式儀表板
   - 制定嵌入式儀表板相關規格 
   - 以新框架重構文字雲、熱門關鍵字；新增熱度圖
2. Trend+ 
   - 將新版熱度圖、文字雲嵌入Trend分析介面，供使用者切換使用
   - 用新版熱門關鍵字取代舊版模組
3. BAM 維運
4. Pickol 維運
5. 其他：檢驗前端團隊分工流程、前端技術分享、因應客戶需求調整開發項目
