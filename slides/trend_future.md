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

# Trend的發展
過去、現在與未來


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
transition: slide-up
---

# Trend的過去
時間：2019.09 - 2022.09

從我進公司且接手Trend前端介面的開發維運，這3年來的改變：

看得見的部分：
 - 跨渠道搜尋頁面：更方便的輸入、更多自訂功能
 - 跨渠道分析頁面：更豐富的圖表、文章檢視、文字雲操作
 - 跨渠道快訊：更明確的建立流程、可依通知時機分組檢視
 - 跨渠道社群群組：更方便的匯入及搜尋社群來源功能

看不見的部分：
 - 用Webpack將程式碼拆分模組化以提高維護效益
 - 參考GitHub flow及Gitlab flow建立開發及維運流程，定義各branch及hotfix流程
 - 用selenium撰寫自動化測試
 - 用Express建立本機端後端程式以提供API進行測試




---

# Trend的現在
Trend依舊是我們公司的主力產品，然而當前卻有幾個課題：
1. 系統穩定性
2. 客戶黏著性
3. 產品競爭力


---
transition: slide-up
---

# Trend的前端框架升級計畫
時間：2021.10 - 至今

跨渠道Trend前端介面已經進入穩定維運階段，AngularJS框架也於2022年1月正式停止提供支援，我認為是時候將Trend介面以新框架重構，並且提供更好的使用者體驗。

因此，在這段期間，我進行了以下工作：
- 與業務一同拜訪客戶，進行使用者經驗研究：https://docs.google.com/presentation/d/156vwyWaG4dvVLgXXxwT7HN7TPsaX9PKl0QRgWasWL74/

- 研究框架之間的優缺點並做成報告，詳見Trend前端框架轉移評估：https://docs.google.com/presentation/d/179sbMunPrvqgbFgyP27BRtf2AzsHfSsIESoRYHgGqEU/

- 實際測試既有產品套件與框架(React, Angular)的相容性:
  - https://github.com/shangjuc/trend_lite_react
  - https://github.com/shangjuc/trend_lite_angular


---

# 從商務帳號管理系統開始的升級計畫
時間：2021.02 - 2022.08 - 至今

主力產品的升級必定是要經過慎密計畫，除了前述UX研究、框架測試，更重要的是建立團隊開發的流程，因此我進行了以下工作：

 - 參與制定需求規格書，與後端討論並制定API串接格式
 - 建立前端團隊開發及維運流程，制定程式碼結構(folders-by-feature structure)、命名規則及版本控制: https://hackmd.io/@5Sce6OMJQfe-_lTBiHiY6g/HkKqpp1Vi
 - 使用TailwindCSS 撰寫元件樣式，以增加元件的可重覆利用性
 - 內部分享介紹TailwindCSS：https://docs.google.com/presentation/d/1qhH7a-dl4xs5m-Vd4kViAWIw0r6kkf5O/
 - 用karma + jasmine撰寫單元測試


---

# Trend的下一步？

1. 情境分析介面？
2. 風向分析模組？
3. 熱門關鍵字介面？




---

# 我們的選擇：情境分析介面
情境分析介面能夠解決前述三大課題：系統穩定性、客戶黏著性、產品競爭力

1. 提升系統穩定性：
   - 將查詢內容限制在某一範圍，讓後端就此範圍的資料進行快取、主動偵錯；
   - 前端採用新框架及狀態管理架構，讓單元測試成為可能；
2. 提升客戶黏著性：
   - 可以讓客戶一次設定、反覆觀看，滿足客戶日常的監看需求；
   - 搭配權限管理(BAM)，可以讓情境模版由使用者選擇是否共享（共同維護使用）；
3. 提升產品競爭力：
	  - 強化既有Trend跨渠道語法自由度和細緻度，維持相比於其他競品的優勢
	  - 借鑑DataStudio模版的優點，產製更貼合我方資料格式的客製化儀表版
    


---

# 情境分析介面能怎麼發展?

- 結合風向分析功能
    - 目前Trend只有FB單一渠道風向分析功能，我們可以直接把跨渠道風向分析模組結合情境分析介面的文章列表，讓使用者在同一介面上直接tag文章
    - 搭配更好看的圖表，讓風向分析功能更有升級感
- 結合熱門關鍵字功能
    - 目前Trend有熱門關鍵字介面，我們可以用權限控制來分享這類頁面，以接觸更多潛在客戶
    - 權限控制也能套用在快訊通知頁面的分享上，讓客戶服務其客戶時，更能彰顯其專業
- Trend輕量化開發構想: https://docs.google.com/presentation/d/1Ih8_hqtwlK-lL63PlVVce0BtpSfiPAzEzBoXziwiEd0/
    - [主題斷詞視覺化圖](https://analytics.qsearch.cc/trend_lite#!?q=%E5%9C%8B%E9%98%B2&panels=ZCP&days=15&channels=FB)
    - [社群影響力趨勢圖](https://analytics.qsearch.cc/trend_lite#!?q=Vtuber&panels=LC&days=30&channels=FB)
    - [貼文互動情緒趨勢圖](https://analytics.qsearch.cc/trend_lite#!?q=Vtuber&panels=BC&days=30&channels=FB)
    - [熱門文章列表](https://analytics.qsearch.cc/trend_lite#!?q=%E5%9C%8B%E8%BB%8DPTT%7C%E5%9C%8B%E8%BB%8D&panels=HP&days=2&channels=FORUM&ptt_filter=Gossiping,HatePolitics,Military)  




---

# 對產品及自身的期許
身為前端開發者對產品發展的想法，也是對自己的要求：
- 在看得見的地方：
  - 提供更好、更穩定的操作介面
  - 提供更佳的使用者體驗
- 在看不見的地方
  - 提升產品的技術等級，讓後續的開發能更快反應市場需求
  - 提升產品的可維護性，讓團隊能夠更有效地維運
- 不斷嘗試新技術，以提供更有趣、更實用的功能給客戶
  - 串接ChatGPT: 以AI輔助客戶建立搜尋語法
  - 串接SlideV: 生成MD文件以自動產製簡報
  - ...


