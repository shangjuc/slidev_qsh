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
---

# Trend 發展方向


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
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
transition: slide-left
---


# Trend產品目前的課題
1. 系統穩定性
2. 客戶黏著性
3. 產品競爭力



---

# 情境分析介面如何解決前述課題?
以下為Trend在新框架中開發情境分析介面為前提:
1. 提升系統穩定性：
    - 將查詢內容限制在某一範圍，讓後端就此範圍的資料進行快取、主動偵錯；
    - 前端採用新框架及狀態管理架構，讓單元測試成為可能；
2. 提升客戶黏著性：
	  - 可以讓客戶一次設定、反覆觀看，滿足客戶日常的監看需求；
	  - 搭配權限管理(BAM)，可以讓情境模版由使用者選擇是否共享（共同維護使用）；
3. 提升產品競爭力：
	  - 強化既有Trend跨渠道語法自由度和細緻度，維持相比於其他競品的優勢；
	  - 借鑑DataStudio模版的優點，產製更貼合我方資料格式的客製化儀表版；

---

# 情境分析介面能怎麼發展?
1. 結合風向分析功能
    - 目前Trend只有FB單一渠道風向分析功能，我們可以直接把跨渠道風向分析模組結合情境分析介面的文章列表，讓使用者在同一介面上直接tag文章
    - 搭配更好看的圖表，讓風向分析功能更有升級感
2. 結合熱門關鍵字功能
    - 目前Trend有熱門關鍵字介面，我們可以用權限控制來分享這類頁面，以接觸更多潛在客戶
3. 權限控制也能套用在快訊通知頁面的分享上，讓客戶服務其客戶時，更能彰顯其專業性

