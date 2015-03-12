## How to make element centered vertically ?

To be honest, this proble is quite annoying because the real world is not as perfect as what you imagine. If you want to **make your element centered vertically**, there are lots of different ways to achieve this in different scenarios. (I really want a attribute that can help us handle all of these.)

### If the element is one-line text and is put inside a container

```html
<p>This is a string</p>
```

```css
p {
  height: 50px;
  line-height: 50px;
}
```

**Pros**
+ Easy to setup.

**Cons**
+ Only for texts.
+ If your text has mult-lines, this hack would break the UI, so this is only for one-line text.

**Demo**
+ http://jsbin.com/ciretajuko/1/edit?html,css,output

### If you already know the size of the element and it resides inside a container

```html
<div class="parent">
  <div class="child"></div>
</div>
```

```css
.parent {
  /* This is important, because the child will be positioned relative to its parent */
  position: relative;
}

/* We assume the size of this element is 100x100, and its display is inline-block */
.child {
  position: absolute;
  top: 50%;
  left: 50%;
  margin-top: -50px; /* -(0.5 * height)px */
  margin-left: -50px; /* -(0.5 * width)px */
}
```

**Pros**
+ This can be used almost in all cases.
+ Almost all browsers (including older ones) can support this.

**Cons**
+ Need some tedius setup.
+ You have to know the exact size of that element first.

**Demo**
+ http://jsbin.com/gajabotusu/1/edit?html,css,output

### If you don't know the size of the element and it resides inside a container

```html
<div class="parent">
  <div class="child"></div>
</div>
```

```css
.parent {
  position: relative;
}

.child {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translateX(-50%) translateY(-50%);
}
```

**Pros**
+ Easy to setup.
+ It can handle various width/height case.

**Cons**
+ We already used `transform` here, so this would make you hard to do some facny UI works on it.
+ IE8 doesn't support transform, but if you focus modern browsers only, then you are good !

**Demo**
+ http://jsbin.com/conaqakuvu/2/edit?html,css,output


** Materials

### Tags
`css`, `vertical`, `center`, `50%`
