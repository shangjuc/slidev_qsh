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
lineNumbers: true
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
---

# QSearch 前端工作任務
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
# QSearch前端年度目標



---
layout: 
---
# 前端年度目標-2023年
時間： 2023年3月～12月31日

1. Trend++ 前端框架升級
   1. Trend 情境分析介面+跨渠道語法編輯器
   2. Trend 熱門文章+風向分析功能
   3. Trend 嵌入式儀表板(文字雲, 熱度圖, 熱門關鍵字)
2. Trend+ 維運
   1. 嵌入Trend++儀表板至既有介面、串接新版API
   2. 用新版功能取代舊有模組(ex.風向分析、熱門關鍵字)
   3. 因應業務團隊需求，調整每季開發項目
3. Pickol 維運



---
layout: intro
---
# QSearch前端季度目標



---
layout: 
---
# 前端季度目標-Q2
時間： 2023年3月～6月30日

1. Trend++ 情境分析介面+跨渠道語法編輯器
   1. 使用者權限控管
   2. 情境分析介面
   3. 跨渠道語法編輯器
   4. 與後端協作儲存情境的API串接
2. Trend+ 跨渠道語法API串接
   1. 從Trend++而來的跨渠道語法必須能被正確讀取及渲染
   2. 串接新版儲存情境API




---
layout: 
---
# 前端季度目標-Q3
時間： 2023年7月1日～9月30日

1. Trend++ 熱門文章+風向分析功能
   1. 重構熱門文章
   2. 整合風向分析功能
   3. 與後端協作風向分析的API串接
2. Trend+ 
   1. 將新版熱門文章嵌入Trend分析介面，供使用者切換使用
   2. 用新版熱門文章+風向分析功能取代舊版模組



---
layout: 
---
# 前端季度目標-Q4
時間： 2023年10月1日～12月31日

1. Trend++ 嵌入式儀表板
   1. 新增熱度圖
   2. 重構文字雲
   3. 重構熱門關鍵字
2. Trend+ 
   1. 將新版熱度圖、文字雲嵌入Trend分析介面，供使用者切換使用
   2. 用新版熱門關鍵字取代舊版模組
