![logo](./assets/logo.png)

# What is ESCSS?

- ESCSS (Enhanced Structure CSS, pronounced "escapes") is a methodology to manage the complexity of CSS structures, inspired by BEM and *The Mythical Man-Month*.

## CSS

### ID:

- Keep HTML clean.
- Easy work with QA team.
- Maintain flat specificity (1,0,0) in general.
- Handle Bootstrap !important situation.


### Status Class:

- Use !important to override id.

```html
<p id="🔥CardList__Title" class="--active">Demo</p>
```

```css
.--active {
  background: red !important;
}
```
or utility class

```html
<p id="🔥CardList__Title" class="!text-red-500">Demo</p>
```

### Developer Experience:

- Increase devtool readability.

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
// BEM way (Not Recommended) - hard to search id
#🔥PersonCard {
  // ...
  &__Img {
    // ...
  }
}
```

### Naming Convention:

- PascalCase: 
  - 🔥CardList (CardList.vue、CardList.jsx ...)
- Only First/Last word is important: 
  - 🔥CardList__Title
  - 🔥CardList__X__X__Img
  - 🔥CardList__X__X2__Name
- Emojis category: 
  - #app(🌀)
  - layout component (📁)
  - page component (📃)
  - component (🔥)
  - reuse component (🔗)

*Emojis are used for visual recognition, but you may have a different preference.*
