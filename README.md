![logo](./assets/logo.png)

# Language

- [中文](./README-zh.md)

## Quick Links

- [What is ESCSS](#what-is-escss)
- [Core Concept - Essence Complexity](#core-concept---essence-complexity)
- [Demo](#demo)
- [Q&A](#qa)

## What is ESCSS?

- ESCSS = extra structure (BEM) CSS + pay tribute to ECMAScript
- ESCSS (pronounced 'escapes') is a Silver Bullet methodology, inspired by The Mythical Man-Month, designed to resolve software dilemmas and reduce developer frustration.

## Core Concept - Essence Complexity

Group similar stuff, extract common elements, and repeat endlessly.

![loop](./assets/loop.gif)

## Demo

![tw](./assets/tw.png)
![scss](./assets/scss.png)
| | HTML | CSS | update speed* | compatibility* |
| - | - | - | - | - |
| Tailwind | 11.01 kB| 8.79 kB | <0.3s | Yes |
| Sass | 8.59 kB| 5.73 kB | ~0.7s| Yes |

****Manual testing, MacBook Air 2020 | intel Core i3 | 8G,***   
****The ability to switch and transition from one party to another***

[repo](https://github.com/ESCSS-labs/demo)

## Q&A

### Why you think ESCSS is the Silver Bullet?

- CSS and JavaScript have consistently ranked in the top three on Stack Overflow for many years and can be used for various purposes, including websites, applications, and games.
- While CSS and JavaScript are easy to use, they can present challenges in maintenance. This is where ESCSS can simplify and enhance the process.
- ESCSS combines object-oriented programming with functional programming styles.

### Demo of the JavaScript part

#### Mutation:

- Mutations can be more efficient than immutable operations.
- Use ESCSS-ESTest to make functions to be pure function.

### Demo of the CSS part

#### ID:

- Keep HTML clean.
- Maintain flat specificity (1,0,0) in general.
- Handle Bootstrap !important situation.

#### Status Class:

- Use !important to override id.

```scss
.--active {
  background: red !important;
}
```

#### Developer Experience:

- Increase devtool readability.
- Recommended example 2 for copy/search/replace

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

#### Naming Convention:

- PascalCase: 🔥CardVue (follows component name for consistency).
- Double Underscore (__): 🔥CardVue__CardText.
- Double hyphen(--) in status class: --dark、--active
- Emojis for organization/readability: Page component (🌀), component (🔥).
- Meaningless element: Follow the element name 🔥Card__X__A、🔥PersonCard__Img.

***This is my favorite version; you might have a different preference.***
