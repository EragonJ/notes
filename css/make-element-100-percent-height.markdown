## How to make element 100% height of browser ?

If you are making a full-page design, normally you will need to set the background to 100% height of the whole browser. But, in order to make this happen, you have to make sure all its parents should be with 100% height like this :

### For parents and grand-parents

```css
html,
body {
  height: 100%;
}

.grandparents,
.parents {
  height: 100%;
}
```

### For that element
```css
.element {
  height: 100%;
}
```

### Tags
`css`, `height`, `100%`, `full-page`
