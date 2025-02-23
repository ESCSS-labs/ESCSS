![logo](./assets/logo.png)

# What is ESCSS?

- Enhanced Structure CSS (pronounced 'escapes') is a methodology for CSS to handle JavaScript safety(BDD), inspired by BEM.

**README is not finished yet**

## CSS

### ID:

- Keep HTML clean.
- Maintain flat specificity (1,0,0) in general.
- Handle Bootstrap !important situation.

### Status Class:

- Use !important to override id.

```scss
.--active {
  background: red !important;
}
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
// BEM way (Not Recommended)
#🔥PersonCard {
  // ...
  &__Img {
    // ...
  }
}
```

### Naming Convention:

- PascalCase: 🔥CardList
- Only First/Last word is important: 🔥CardList__X__X__Img、🔥CardList__X__X2__Name、🔥CardList__Title.
- Emojis category: page/layout component (🌀), component (🔥). reuse component(🔗)

***This is my style, you may have different preferences.***
