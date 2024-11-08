![logo](./assets/logo.png)

## 快速連結

- [什麼是 ESCSS](#什麼是-escss)
- [例子](#例子)
- [問與答](#問與答)

## 什麼是 ESCSS?

- ESCSS (pronounced 'escapes') = Enhanced Structure (BEM) CSS。

## 例子
### ESCSS-ESTest 錯誤日誌演示
ESCSS-ESTest 的線上錯誤演示，協助提升工作效率的工具。
![estest](./assets/demo-estest.png)

#### 技術
  - ESCSS
  - ESCSS-SCSS
  - ESCSS-ESTest

#### 資訊
- [Demo site](https://demo-estest-log-not-visible.netlify.app/)
- [Repository](https://github.com/ESCSS-labs/demo-estest-log-not-visible)

### 天堂衝裝模擬器
早期 Vue 3 個人作品，加入了測試來保護程式碼，並進行內部重構與優化，最終升級至 Nuxt 3。

![lineage](/assets/lineage-demo.png)

#### 技術
  - ESCSS
  - ESCSS-SCSS
  - ESCSS-ESTest
  - Playwright (E2E)
  - Vue 3/ Nuxt 3
  - Pinia

#### 資訊
- [Demo site](https://lineage-gear-enhancement-simulator.netlify.app/)
- [Repository](https://github.com/ESCSS-labs/demo-lineage-gear-enhancement-simulator)

### Nike 網站
在一個工作天內完成了對 React Nike 的 Tailwind 專案的 Fork 重構，最終畫面的呈現保持一致。

![demo-nike](./assets/demo-nike.png)

#### 技術
  - ESCSS
  - ESCSS-SCSS
  - Tailwind

#### 資訊
- [Original Version](https://niike.vercel.app/)
- [Refactored Version](https://demo-nike.vercel.app/)
- [Repository](https://github.com/ESCSS-labs/demo-nike?tab=readme-ov-file)

### Clone Tailwind playground
![tailwind](/assets/tailwind-demo.png)
參考 Tailwind playground 網站。並對內部結構進行重構和優化，確保最終呈現的畫面保持一致。

#### 技術
  - ESCSS
  - ESCSS-SCSS
  - Tailwind

#### 資訊
- [Original Version](https://play.tailwindcss.com/)
- [Refactored Version](https://demo-tailwind-playground.netlify.app/)
- [Repository](https://github.com/ESCSS-labs/demo-tailwind-playground)

## 問與答

### CSS

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

```scss
// Easy to copy/search/replace (Recommended)
#🔥PersonCard {
  // ...
}

#🔥PersonCard__Img {
  // ...
}
```

```scss
// BEM way (Not Recommended)
#🔥PersonCard {
  // ...
  &__Img {
    // ...
  }
}
```

#### 命名風格:

- PascalCase: 🔥CardVue (遵循組件名稱以保持一致性)。
- 雙下劃線 (__): 🔥CardVue__CardText。
- 狀態 class 的雙連字符 (--): --dark、--active。
- 使用表情符號以增強組織性/可讀性: 頁面元件 (🌀), 元件 (🔥)。
- 無意義元素: 遵循元素名稱 🔥Card__X__A、🔥PersonCard__Img。

***這是我的風格，你可能有不同的偏好。***
