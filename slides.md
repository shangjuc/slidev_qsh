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

# 淺談前端狀態管理

使用者權限控管

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    開始 <carbon:arrow-right class="inline"/>
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


# 何謂狀態(state)?
在前端，狀態就是介面上的變數，可以隨著使用者操作而變化。

常見的狀態：
- 使用者登入狀態
- 購物車狀態
- 訊息狀態

Trend常見的狀態(state)：
- 使用者登入狀態
- 系統更新通知狀態
- 語法編輯、設定社群群組、快訊等等操作狀態

<br>

> 參考資料： [有關前端的狀態管理](https://ithelp.ithome.com.tw/articles/10191884)


---
transition: slide-left
---

# 何謂狀態管理(state management)?
由於HTML基本上是無狀態的(stateless)，但前端介面需要將使用者操作的狀態留存下來以繼續使用，並且確保狀態的變化是正確的，此即狀態管理。

「一般而言，前端工程師會使用像是 Cookie, local storage... 等等瀏覽器端的儲存藉由跟後端的連結來統一處理狀態問題，因為涉及不同的頁面都會使用到這些狀態，譬如使用者登入狀態會影響可以允許進入的網頁，前端必須要統一處理這些狀態，以免造成狀態不及時造成的問題。」

<br>
<br>

> 參考資料： [有關前端的狀態管理](https://ithelp.ithome.com.tw/articles/10191884)

---
transition: slide-left
---

# 因應複雜狀態管理而生的Flux架構
「Flux 並不是一個 Library，它是一種應用程式的架構 (application architecture)，就像常看到的 MVC (Model View Controller) 一樣是一種架構」

FB訊息已讀/未讀顯示錯誤的bug:
<img src="https://s3-us-west-1.amazonaws.com/angular-academy/blog/images/facebook-bug.png"/>

> The problem was that the unread messages counter was systematically displaying incorrect results: users would see for example one unread message, then they would click on the counter and all the messages had already been read.

隨著上述問題，Flux架構相應而生，且各主流前端框架皆有對應的狀態管理工具：
- React: Redux
- Angular2+: NgRx/store
- Vue: Vuex

<br>

> 參考資料： [Flux 的基本概念](https://ithelp.ithome.com.tw/articles/10192962), [Ngrx Store - An Architecture Guide](https://blog.angular-university.io/angular-ngrx-store-and-effects-crash-course/)

<style>
  img{
    float: right;
    width: 100px
  }
</style>

---
transition: slide-left
---

# Flux架構的主要概念
Flux是一種狀態管理架構，它大致可以分成四個部分。

```html {0|1|2|3|4|all}
- Action: 對應於使用者的操作所定義的動作。
- Dispatcher: 接受Actions的單一窗口，在每個applicatoin中，Dispatcher 只會有一個。
- Store: 儲存Reducers。Reducer是「在某組相對應的State及Action下要回呼的函式」，其會將Action與舊State化約為新State。
- View: 使用者看到的內容，其會隨著狀態改變。
```

<arrow v-click="1" x1="200" y1="450" x2="200" y2="400" color="#564" width="3" arrowSize="1" />
<arrow v-click="2" x1="400" y1="450" x2="400" y2="400" color="#564" width="3" arrowSize="1" />
<arrow v-click="3" x1="600" y1="450" x2="600" y2="400" color="#564" width="3" arrowSize="1" />
<arrow v-click="4" x1="800" y1="450" x2="800" y2="400" color="#564" width="3" arrowSize="1" />
<br>
<img src='https://facebook.github.io/flux/img/overview/flux-simple-f8-diagram-1300w.png'>

<br>

> 參考資料： [Flux: In-Depth Overview](https://facebook.github.io/flux/docs/in-depth-overview.html#content)

---
transition: slide-left
---

# Flux架構的資料流是單向的
Flux架構中，使用者在View的操作無法直接改變狀態，而必須以Action的方式回到架構中跑流程去改變狀態。

```html {1|2|3|all}
Data in a Flux application flows in a single direction.
The views may cause a new action to be propagated through the system in response to user interactions. 
「特別注意的是它的方向性，它一定是單向的。也就是說 View 不能直接改變狀態，一定要透過 Dispatcher」
```

<img src='https://facebook.github.io/flux/img/overview/flux-simple-f8-diagram-with-client-action-1300w.png'>

<br>

> 參考資料：[Flux: In-Depth Overview](https://facebook.github.io/flux/docs/in-depth-overview.html#content), [更改狀態的基礎 Action & Reducer](https://fullstackladder.dev/blog/2022/08/03/ngrx-04-action-reducer/)

---
transition: slide-left
---

# Redux的狀態管理資料流

<div class="img-container">
  <img src='https://d33wubrfki0l68.cloudfront.net/01cc198232551a7e180f4e9e327b5ab22d9d14e7/b33f4/assets/images/reduxdataflowdiagram-49fa8c3968371d9ef6f2a1486bd40a26.gif'>
</div>


<br>
<br>

> 參考資料：[Redux Application Data Flow](https://redux.js.org/tutorials/fundamentals/part-2-concepts-data-flow)


<style>

.img-container {
  display: flex;
  justify-content: center;
  height: 75%;
}
img {
  height: 100%;
}
</style>



---
transition: slide-left
---

# NgRx狀態管理資料流
Angular2+ NgRx
<div class="img-container">
  <img src='https://ngrx.io/generated/images/guide/store/state-management-lifecycle.png
'>
</div>


<br>
<br>

>參考資料：[@ngrx/store](https://ngrx.io/guide/store)


<style>

.img-container {
  display: flex;
  justify-content: center;
  height: 75%;
}
img {
  height: 100%;
}
</style>


---
transition: slide-left
---

# 在什麼時候可以考慮使用Flux架構？
我們可以參考NgRx提出的SHARI準則，在這些情況時，可能需要使用Flux架構的狀態管理。

A good guideline that might help answer the question, "Do I need NgRx Store?" is the SHARI principle:

```html {1,2|3,4|5,6|7,8|9,10|all}
- Shared: state that is accessed by many components and services. 
  狀態被多個元件或服務共享。
- Hydrated: state that is persisted and rehydrated from external storage. 
  狀態是持久的且從外部儲存合成，例如localStorage
- Available: state that needs to be available when re-entering routes. 
  狀態在使用者再次進入同一路由時要能繼續使用
- Retrieved: state that must be retrieved with a side-effect. 
  狀態取用時必然伴隨著副作用。
- Impacted: state that is impacted by actions from other sources. 
  狀態會受其他來源的動作所影響。
```


> 參考資料：[Ngrx Store - An Architecture Guide](https://blog.angular-university.io/angular-ngrx-store-and-effects-crash-course/)


---
transition: slide-left
---

# 使用Flux架構的狀態管理有什麼好處？
總結來說，有以下優點：
- 方便使用外部儲存：
  - Persist state to a LocalStorage
  - Pre-fill state on the server
- 易於追縱狀態在「何時」被「何者」「如何」改變：
  - Flux架構會將「使用者的動作Action與當下的狀態State的組合」序列化，單向資料流讓錯誤易於重現。
  - 瀏覽器有相應的擴充功能Redux DevTool可以協助追縱狀態流程。
- 易於測試：
  - 由於Store裡的Reducer必須是純函數，因此易於進行單元測試
  - Test-driven development

<!-- 
```html {1|2|3|4|5|6|7|8|0}
- Persist state to a local storage and then boot up from it, out of the box.
- Pre-fill state on the server, send it to the client in HTML, and boot up from it, out of the box.
- Serialize user actions and attach them, together with a state snapshot, to automated bug reports, so that the product developers can replay them to reproduce the errors.
- Pass action objects over the network to implement collaborative environments without dramatic changes to how the code is written.
- Maintain an undo history or implement optimistic mutations without dramatic changes to how the code is written.
- Travel between the state history in development, and re-evaluate the current state from the action history when the code changes, a la TDD.
- Provide full inspection and control capabilities to the development tooling so that product developers can build custom tools for their apps.
- Provide alternative UIs while reusing most of the business logic.
``` -->
<!-- 
```html {0|1|2,3|4|5,6|0}
- 在撰寫程式的過程，就會開始把所有狀態、行為和邏輯拆到這些角色中，之後在 Component 內就會變得很單純
  - 讀取狀態：從 Selector 拿資料就好
  - 改變狀態：分配 Action 就好
- 當所有資料流向都很單純，要追查問題就會變得很簡單
  - 讀取狀態有問題，就往讀取狀態那條資料流（Selector）追查 
  - 寫入狀態有問題，就往寫入狀態那條資料流（Reducer）追查
``` -->
<!-- 
```html {0|1|2|3}
- 可追蹤：因為有了Chrome extention 的 Redux DevTool，可以清楚了解狀態改變的流程，以進行對可能存在的程式錯誤做除錯。
- 增加效能：對一些 Component 的 ChangeDetectionStrategy 為 OnPush
- 易於測試：因為 Reducer 是純函數，便於測試
``` -->
<br>

> 參考資料： [You Might Not Need Redux](https://medium.com/@dan_abramov/you-might-not-need-redux-be46360cf367), [ngrx/store 完成篇](https://ithelp.ithome.com.tw/articles/10197238), [簡介 NgRx](https://fullstackladder.dev/blog/2022/04/17/ngrx-01-introduce/)


---
transition: slide-left
---
# 中場休息時間
接下來將會進行Flux架構的實作


---
transition: slide-left
---

# Redux狀態管理的實作準則

Redux offers a tradeoff. It asks you to:

- Describe application state as **plain objects and arrays**.
- Describe changes in the system as **plain objects**.
- Describe the logic for handling changes as **pure functions**.

<br>
<br>

> Read more about [You Might Not Need Redux](https://medium.com/@dan_abramov/you-might-not-need-redux-be46360cf367)


---
transition: slide-left
---


# Reducer必須為純函數
在Redux裡，要求使用純函數處理狀態的變化。以下為純函數的定義[^1]，其必須符合兩個條件：

> - The function return values are identical for identical arguments (no variation with local static variables, non-local variables, mutable reference arguments or input streams)
> - The function has no side effects (no mutation of local static variables, non-local variables, mutable reference arguments or input/output streams).

在前端的純函數：
1. 「函數對於同樣的參數，永遠產生同樣的結果，也就是這個函數不能根據一些隱藏資訊（例如函數內使用全域變數，亂數...）或者目前的狀態在程式執行時（例如目前時間,目前頁面...），程式與程式之間 (在不同的函數呼叫此函數時），或者使用者輸出入介面(I/O)的值（例如 event listener對於 input, mouseMove, 跟後端伺服器做 request...)。」
2. 「函數產生的結果，不能帶來副作用(side effect)或者輸出,也就是不能對可變動的物件(mutable object)做更動，或者使用者輸出介面做輸出。」


> [^1 Pure function](https://en.wikipedia.org/wiki/Pure_function), [純函數 (Pure Function)](https://ithelp.ithome.com.tw/articles/10193249)

---
transition: slide-left
---


# 純函數與不純函數
純函數與不純函數
純函數的例子
```js {all|1,2,3|4,5|all}
function sum(a, b) {
  return a + b;
}
sum(2,5);
// will always return 7
```

不純函數的例子
```js {all|1|2,3,4|5,6|9|10,11|all}
var discount = 0.8;
function calcPrice(price) {
  return price * discount;
}
console.log(calcPrice(100));
// will return 80
// however when discount var change
var discount = 0.9;
console.log(calcPrice(100));
// now will return 90
``` 
> [Pure function](https://en.wikipedia.org/wiki/Pure_function), [純函數 (Pure Function)](https://ithelp.ithome.com.tw/articles/10193249)


<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
</style>

--- 
transition: slide-left
---

# 參考資料

[Documentations](https://sli.dev) · [GitHub](https://github.com/slidevjs/slidev) · [Showcases](https://sli.dev/showcases.html)

- [有關前端的狀態管理](https://ithelp.ithome.com.tw/articles/10191884)
- [Flux 的基本概念](https://ithelp.ithome.com.tw/articles/10192962)
- [Ngrx Store - An Architecture Guide](https://blog.angular-university.io/angular-ngrx-store-and-effects-crash-course/);
- [Flux: In-Depth Overview](https://facebook.github.io/flux/docs/in-depth-overview.html#content)
- [更改狀態的基礎 Action & Reducer](https://fullstackladder.dev/blog/2022/08/03/ngrx-04-action-reducer/)
- [Redux Application Data Flow](https://redux.js.org/tutorials/fundamentals/part-2-concepts-data-flow)
- [@ngrx/store](https://ngrx.io/guide/store)
- [ngrx/store 完成篇](https://ithelp.ithome.com.tw/articles/10197238)
- [You Might Not Need Redux](https://medium.com/@dan_abramov/you-might-not-need-redux-be46360cf367)
