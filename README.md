## Responsive Flex layout

---

### intro

The layout is built using bulma css library. Bulma is installed through `npm`.

```javascript
npm install bulma --save-dev
```

`node-sass` is used to compile bulma sass files to css

### Prerequisites

1. node

---

### installation

run

```javascript
npm install
```

---

### Code

Bulma is imported in the main.scss file located in `layout\main.scss`.

main.scss

```css
@import "../node_modules/bulma/bulma.sass";
```

npm scripts are used to run node-sass for compilation, the csss is saved into `style.css` located in `layout\style.css`

scripts

```javascript
 "scripts": {
    "build-sass": "node-sass layout/main.scss  layout/style.css",
    "watch-sass": "node-sass layout/main.scss  layout/style.css -- --watch"
  }
```

Run the script to either compile or watch the scss.

---

### bulma

Since this setup is only anout flex and layout responsive ness, other bulma styling features such as element styling have been removed. The main styling file is `@import "sass/grid/_all"`

The main bulma file is at `node_modules\bulma\bulma.sass`

Get more info from [Bulma Docs](https://bulma.io/documentation/overview)

---

## Easy use case

#### Creating columns

we first create a container called `columns` that holds each individual column

```html
<div class="columns">
  <div class="column">First column</div>
  <div class="column">Second column</div>
  <div class="column">Third column</div>
  <div class="column">Fourth column</div>
</div>
```

The above columns will be automatically responsive

---

## Column widths

1. Different column widths can be set for different devices using

```css
s-three-quarters-mobile
is-two-thirds-tablet
is-half-desktop
is-one-third-widescreen
is-one-quarter-fullhd
```

example

```html
<div class="column  is-three-quarters-mobile">First column</div>

<div class="column  is-half-desktop">Third column</div>
```

2. Sizes using multiples of 20%:

```css
is-one-fifth
is-one-quarter
is-one-third
is-two-fifths
is-half
is-three-fifths
is-two-thirds
is-three-quarters
is-four-fifths
is-full
```

example

```html
<div class="column is-two-fifths">Fourth column</div>
```

3. sizes using grid naming

used by assigning a column a name:

```css
is [number]
```

where number is between 1 - 12, a larger number will produce a greater width:

```css
is 8
```

example

```html
<div class="column is-3">Second column</div>
```

---

### Offset

used to align a column in a horizontal position. created using

```css
is-offset-one-quarter
is-offset-one-fifth
is-offset-8
is-offset-1
```

example

```html
<div class="column is-5  is-offset-one-quarter">main</div>
```

### Narrow

used to specify that the column to only take the space it needs.

Narrow can be set for different divices

```css
.is-narrow-mobile
  .is-narrow-tablet
  .is-narrow-touch
  .is-narrow-desktop
  .is-narrow-widescreen
  .is-narrow-fullhd;
```

example

```html
<div class="column is-narrow">
  <div class="box" style="width: 200px;">
    <p class="title is-5">Narrow column</p>
    <p class="subtitle">This column is only 200px wide.</p>
  </div>
</div>
```

---

### Mobile stack

To activates columns for mobile also we use ` is-mobile` on the column container.
This will prevent stacking of columns on mobile

```html
<div class="columns  is-mobile ">
  <!---column-->
</div>
```

---

### Gaps

To remove gaps use 1 ` is-gapless` on the column parent

```html
<div class="columns  is-mobile  is-gapless">
  <!---column-->
</div>
```

#### Gap variables

used to specify a gap between the columns, can use `is` and value between 0 - 8

```css
is-[number]

```

```css
is-2
```

---

To align columns vertically use `is-vcentered` on the columns parent

---

### Project layouts

The project layouts can be found in the layout folder

#### Views

> #### 1. (1 of 1) and (1 of 2) and (2 of 2) containers
>
> #### 2. (1 of 3) and (3 of 3) containers
>
> #### 3. (1 of 4) and (4 of 4) containers
>
> #### 4. (1 of 5) and (5 of 5) containers
>
> #### 5. (1 of 8) and (8 of 8) containers
>
> #### 6. (1 of 12) and (12 of 12) containers
>
> #### 5. Nested containers

---

### custom styling

### `custom.scss` is used to style the columns. `layout\custom.scss`

```css
 1. background-image: linear-gradient(25deg, #6679c1, #998da4, #bda285, #dbb861);
 2. box-shadow: 5px 10px 10px #0000003d;

```

### Delete custom.scss and replace it with your styling code. Remove the import in main.scss

---

### Documentations at [bulma.io](https://bulma.io/documentation/)
