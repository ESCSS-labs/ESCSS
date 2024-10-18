![logo](./assets/logo.png)

## 快速連結

- [什麼是 ESCSS](#什麼是-escss)
- [核心概念 - 本質複雜性](#核心概念---本質複雜性essential-complexity)
- [例子](#例子)
- [問與答](#問與答)

## 什麼是 ESCSS?

- ESCSS = extra structure (BEM) CSS + 致敬 ECMAScript
- ESCSS (發音如同 'escapes') 是一種銀彈方法論，靈感來自《人月神話》一書，旨在解決軟體困境，減少開發者的挫敗感。

## 核心概念 - 本質複雜性(essential complexity)

將相似的事物分組，提取共同元素，並不斷重複。

![loop](./assets/loop.gif)

## 例子

用 CardVue.vue(component) 來演示，並且使用 [ESCSS-ESTest](https://github.com/ESCSS-labs/ESCSS-ESTest) & [ESCSS-SCSS](https://github.com/ESCSS-labs/ESCSS-SCSS)

```vue
<script setup>
import { ESTest } from "escss-estest";

const CardVue = {
  data: {
    enable: true,
  },
  in: {
    reuse: {
      getWord: (word) => {
        {
          ESTest(word, "string", "mike 09092024 4");
        }

        console.log(word);
      },
    },
    getGreeting: () => {
      CardVue.in.reuse.getWord("Hello world");
    },
  },
  out: {
    sum: (a, b) => {
      {
        ESTest(a, "number", "mike 09092024 1");
        ESTest(b, "number", "mike 09092024 2");
        ESTest(CardVue.data.enable, "===", true, "mike 09092024 3");
      }

      CardVue.in.getGreeting();
      return a + b;
    },
  },
};

CardVue.out.sum(1, 2);
</script>

<template>
  <main>
    <div id="🔥PersonCard">
      <img
        id="🔥PersonCard__Img"
        src="https://tailwindcss.com/img/erin-lindford.jpg"
        alt="Woman's Face"
      />
      <div id="🔥PersonCard__Div">
        <div id="🔥PersonCard__Div__Box">
          <p id="🔥PersonCard__Div__Box__Name">Erin Lindford</p>
          <p id="🔥PersonCard__Div__Box__Title">Product Engineer</p>
        </div>
        <button id="🔥PersonCard__Div__Button">Message</button>
      </div>
    </div>

    <div id="🍎UIComponent">
      An UI component
    </div>
  </main>
</template>

<style lang="scss">
@include utils_base-preflight-v3-modify; // 內建的 base css

// 這只是直接從 tailwind 轉化成 scss
#🍎UIComponent {
  margin-top: 20px; // 使用 css
  @include bg-green-300; // 使用 tailwind
  @include utils_reset-tw; // 重置某些 tailwind 變數
}

#🔥PersonCard {
  @include py-8;
  @include px-8;
  @include max-w-sm;
  @include mx-auto;
  @include bg-white;
  @include rounded-xl;
  @include shadow-lg;
  @include space-y-2;

  @include sm {
    @include py-4;
    @include flex;
    @include items-center;
    @include space-y-0;
    @include space-x-6;
  }

  @include utils_reset-tw;
}

#🔥PersonCard__Img {
  @include block;
  @include mx-auto;
  @include h-24;
  @include rounded-full;

  @include sm {
    @include mx-0;
    @include shrink-0;
  }

  @include utils_reset-tw;
}

#🔥PersonCard__Div {
  @include text-center;
  @include space-y-2;

  @include sm {
    @include text-left;
  }

  @include utils_reset-tw;
}

#🔥PersonCard__Div__Box {
  @include space-y-0\.5;
  @include utils_reset-tw;
}

#🔥PersonCard__Div__Box__Name {
  @include text-lg;
  @include font-semibold;
  @include utils_reset-tw;
}

#🔥PersonCard__Div__Box__Title {
  @include text-slate-500;
  @include font-medium;
  @include utils_reset-tw;
}

#🔥PersonCard__Div__Button {
  @include px-4;
  @include py-1;
  @include text-sm;
  @include text-purple-600;
  @include font-semibold;
  @include rounded-full;
  @include border;
  @include border-purple-200;

  &:hover {
    @include text-white;
    @include bg-purple-600;
    @include border-transparent;
  }

  &:focus {
    @include outline-none;
    @include ring-offset-2;
    @include ring-2;
    @include ring-purple-600;
  }

  @include utils_reset-tw;
}
</style>
```

![demo](./assets/demo.png)

## 問與答

### 為什麼你認為 ESCSS 是銀彈嗎？?

- CSS 和 JavaScript 自多年來年一直居於 Stack Overflow 的排行榜中的前三名，並且可以用於網站、應用程序和遊戲等不同用途。
- CSS 和 JavaScript 易於使用，但維護起來可能具有挑戰性。這就是 ESCSS 可以簡化和增強的部分。
- ESCSS 將物件導向與函數編成風格結合。

### JavaScript部分的演示

#### 可變性(Mutation):

- 我認為可變性比不可變性操作更有效率.
- 使用 ESCSS-ESTest 來創建純函數.

### CSS部分的演示

#### ID:

- 保持 HTML 的簡潔。
- 通常維護扁平化的特異性(1,0,0)。
- 處理 Bootstrap 中的 !important 情況。

#### 狀態 Class:

- 使用 !important 覆蓋 id.

```scss
.--active {
  background: red !important;
}
```

#### 開發者體驗:

- 提高開發工具的可讀性。.
- 建議使用 example 2 以便於複製/搜索/替換。

```scss
// example 1
 #🔥PersonCard {
  // ...
  &__Img {
    // ...
  }
}

// example 2
 #🔥PersonCard {
  // ...
}
#🔥PersonCard__Img {
  // ...
}
```

#### 命名風格:

- PascalCase: 🔥CardVue (遵循組件名稱以保持一致性)。
- 雙下劃線 (__): 🔥CardBox__CardText。
- 狀態 class 的雙連字符 (--): --dark、--active。
- 使用表情符號以增強組織性/可讀性: 頁面元件 (🌀), 元件 (🔥)。
- 無意義元素: 遵循元素名稱 🔥Card__Box__A、🔥PersonCard__Img。

***這是只是我最喜歡的風格，你可能有不同的偏好。***
