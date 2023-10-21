### HTML Formatting

<details>
  <summary>Use <b>2 spaces</b> for indentation in your file (not a <code>tab</code> character)</summary>

  > to make sure your formatting will look the same everiwhere
</details>

<details>
  <summary>Remember about correct indentation between parent and child elements</summary>

  > Each level of nesting, including text, contained inside the element, requires 2-space offset. 
  Also blank line shouldn't be between parent and child elements.

  GOOD example
  ```html
  <body>
    <div>
      <p>
        Awesome text
      </p>
    </div>
  </body>
  ```

  BAD example
  ```html
  <body>
  <div>
  <p>
  Awesome text
  </p>
  </div>
  </body>
  ```
</details>

<details>
  <summary>Add empty lines between multiline sibling blocks of HTML</summary>

  > To add some "air" and simplify reading. But don't add them between parent and child elements.

  GOOD Example
  ```html
  <ul>
    <li class="nav__item">
      <a href="#home">Home</a>
    </li>

    <li class="nav__item">
      <a href="#shop">Shop</a>
    </li>

    <li class="nav__item">
      <a href="#contacts">Contacts</a>
    </li>
  </ul>
  ```

  BAD Example
  ```html
  <ul>

    <li class="nav__item">
      <a href="#home">Home</a>
    </li>
    <li class="nav__item">
      <a href="#shop">Shop</a>
    </li>
    <li class="nav__item">
      <a href="#contacts">Contacts</a>
    </li>

  </ul>
  ```
</details>

<details>
  <summary>Keep your attributes correctly formatted</summary>

  > If the HTML-element has long attribute values or number of attributes is more than 2 - start each one,
  including the first, on the new line with 2-space indentation related to tag.
  Tag’s closing bracket should be on the same level as opening one.

  GOOD Example
  ```html
  <input
    type="text" 
    name="surname" 
    id="surname"
    required
  >
  ```

  BAD Examples
  ```html
  <input type="text" name="surname" 
         id="surname" required>

  <input type="text" 
         name="surname" 
         id="surname"
         required>

  <input
  type="text" 
  name="surname" 
  id="surname"
  required>

  <input
    type="text" 
    name="surname" 
    id="surname"
    required>
  ```
</details>

<details>
  <summary>Lines of code have <code>80</code> chars max</summary>
  
  > It is just easier to read such lines
</details>

### HTML Content

<details>
  <summary>Use semantic tags where possible</summary>

  > Like `header`, `section`, `article`, `p`. It improves your page SEO and helps screen readers. `div` and `span` does not have any meaning
</details>

<details>
  <summary> <code>alt</code> attribute should describe the image content</summary>


  GOOD example
  ```html
  <img alt="Samsung Galaxy S22 2022 8/128GB Green" />
  ```

  REALLY BAD example
  ```html
  <img alt="image" />
  ```

  STILL BAD example
  ```html
  <img alt="phone" />
  ```
</details>

<details>
  <summary>Class names represent the meaning of the content (not the styles or tag names)</summary>

  GOOD example
  ```html
  <nav class="nav">
    <ul class="nav__list">
      ...
      <li class="nav__item">
        <a href="#apple" class="nav__link">Apple</a>
      </li>
    </ul>
  </nav>
  ```

  BAD example
  ```html
  <nav class="no-padding">
    <ul>
      ...
      <li class="li">
        <a href="#apple" class="a-last-no-decoration">Apple</a>
      </li>
    </ul>
  </nav>
  ```
</details>

<details>
  <summary>Don't use spaces in links</summary>

  > Have you seen any link with literal space in it on the Internet? Remember, anchor links start with `#`
</details>

### CSS
<details>
  <summary>Don't use <code>*</code> selector (it impacts performance)</summary>

  > Set styles only for elements that require them.
  > Zeroing out your margins, paddings or other styles with '*' is still inefficient for browser.
</details>

<details>
  <summary>Don't use tag names for styling (except <code>html</code> and <code>body</code>)</summary>

  > Style all elements using `.classes` and if needed with `:pseudo-classes`, `pseudo-elements` and `[attributes]`

  HTML Example
  ```html
  <nav class="nav">  
    <ul class="nav__list">  
      ...  
    <ul>  
  </nav>  
  ```

  GOOD CSS Example
  ```css
  .nav__list {
    list-style: none
  }
  ```

  BAD CSS Examples
  ```css
  ul {
    list-style: none
  }

  nav ul {
    list-style: none
  }
  ```
</details>

<details>
  <summary>Remember to use fallback fonts - alternative font-family in case the main one doesn't work</summary>
  
  > [Explanation](https://www.w3schools.com/cssref/pr_font_font-family.asp)
</details>

<details>
  <summary>Be consistent with your margins (Add only top or bottom, but not both)</summary>

  > To avoid potential margin collapse
</details>

<details>
  <summary>Don't fix container size (if there is no such a requirement)</summary>

  > Let the content size dictate it. To avoid overflow or accidental scroll bar
</details>

<details>
  <summary>
    Hightlight clickable element with <code>cursor: pointer</code> and some <code>:hover</code> styles
  </summary>

  > It improves UX, and help users understand the page better
</details>

### BEM

<details>
  <summary>Create a separate file per each styles block</summary>

  - If styles block has the same name as BEM block - create separate file for it
</details>

<details>
  <summary>Follow naming convention <code>block__element--modifier</code></summary>

  ```html
  <div class="block-name block-name--modifier-name--modifier-value">
    <p class="block-name__element-name block-name__element-name--modifier-name">
      text
    </p>
  </div>
  ```
</details>

### SASS

<details>
  <summary>Check your import syntax. It's differs from plain CSS</summary>

  ```css
  /* CSS */
  @import url("filename.css");
  ```

  ```scss
  /* SCSS */
  @import "filename";
  ```
</details>

<details>
  <summary>Use variables for the main values</summary>

  - Create variables only when value repeats more than once.
  - Use descriptive names.
</details>

<details>
  <summary>Don't use loops for styles that stay the same</summary>

  - display and position are perfect examples for styles that stay the same.
</details>

<details>
  <summary>Use mixins, functions, etc.</summary>

  - These are powerful tools to get rid of repeatable code, but don't use them everywhere.
</details>

<details>
  <summary>Use nesting</summary>

  - Write pseudo-class, pseudo-element selectors inside general selector. As well as media queries.

  GOOD Example
  ```scss
  &__buy-link {
    display: flex;
    margin-top: 20px;

    &:hover {
      color: blue;
    }
  }
  ```

  BAD Example
  ```scss
  &__buy-link {
    display: flex;
    margin-top: 20px;
  }

  &__buy-link:hover {
    color: blue;
  }
  ```
</details>

### Typical BEM Mistakes in HTML

<details>
  <summary>An Element of Another Element</summary>

  > An element belongs to a block, not to another element. 
  > That's why the **prefix** — is the name of a block, not the name of another element.

  ```html
  <div class="example">
    <ul class="example__list">

      <!-- Wrong -->
      <li class="example__list__item">...</li>
      
      <!-- Correct -->
      <li class="example__item">...</li>

    </ul>
  </div>
  ```
</details>

<details>
  <summary>Using an Element Without Its Block's Prefix</summary>

> The name of an element MUST contain the name of its block.

```html
<!-- Wrong -->
<ul class="menu">
  <li class="item">
    Only if it's not a standalone block
  </li>
</ul>

<!-- Correct -->
<ul class="menu">
  <li class="menu__item">...</li>
</ul>
```

</details>
<details>
  <summary>Using a Modifier Instead of an Element</summary>

> Double underscore is used to separate the name of a block and the name of an element. 

```html
<!-- Wrong -->
<ul class="menu">
  <li class="menu--item">...</li>
  <li class="menu_item">...</li>
</ul>

<!-- Correct -->
<ul class="menu">
  <li class="menu__item">...</li>
  <li class="menu__item">...</li>
</ul>
```

</details>
<details>
  <summary>Using a Modifier Without the Belonging Class</summary>

> A modifier **must not** be used without the class it modifies.

```html
<!-- Wrong -->
<ul class="menu--mobile">
  <li class="menu__item--active">...</li>
</ul>

<!-- Correct -->
<ul class="menu menu--mobile">
  <li class="menu__item menu__item--active">...</li>
</ul>
```

</details>
<details>
  <summary>Using a Block Modifier on an Element</summary>

> A block modifier **must not** be used on the block's elements.

```html
<!-- Wrong -->
<ul class="menu">
  <li class="menu__item menu--active">...</li>
</ul>

<!-- Correct -->
<ul class="menu">
  <li class="menu__item menu__item--active">...</li>
</ul>
```

</details>
<details>
  <summary>Using a Modifier Without a Prefix</summary>

> An element modifier **must** be preceded by the name of the element, the same is true for block modifiers.

```html
<!-- Wrong -->
<nav class="nav fixed">
  <a class="nav__link active" href="#">
    Wrong
  </a>
</nav>

<!-- Correct -->
<nav class="nav nav--fixed">
  <a class="nav__link nav__link--active" href="#">
    Correct
  </a>
</nav>
```

</details>
<details>
  <summary>Using an Element Inside Another Block</summary>

> An element of the parent block **must not** be used inside a child block.

```html
<div class="parent">
  <!-- Wrong -->
  <div class="child">
    <p class="parent__element">Text</p>
  </div>
  
  <!-- Correct -->
  <div class="child parent__element">
    <p class="child__element">Text</p>
  </div>
</div>
```

</details>
<details>
  <summary>Using an Element Outside a Block</summary>

> An element **must not** be used outside the block it belongs to.

```html
<!-- Wrong -->
<div class="block">
  Content
</div>

<p class="block__element">Text</p>

<!-- Correct -->
<div class="block">
  <p class="block__element">Text</p>
</div>
```

</details>
<details>
  <summary>Using Different Naming Conventions Within One Project</summary>

> Using different [naming conventions](https://en.bem.info/methodology/naming-convention/) within one project is not allowed.

```html
<!-- Wrong -->
<div class="ParentBlock ParentBlock_mobile">
  <div class="child-block child-block--active ParentBlock-element"></div>
</div>

<!-- Correct -->
<div class="ParentBlock ParentBlock_mobile">
  <div class="ChildBlock ChildBlock--active ParentBlock-element"></div>
</div>

<!-- Correct -->
<div class="parent-block parent-block--mobile">
  <div class="child-block child-block--active parent-block__element"></div>
</div>
```
</details>

### Typical BEM Mistakes in CSS

<details>
  <summary>Styling an Element in the Context of Another Element</summary>

> Styles of one element **must not** depend on its relations with other elements.

```html
<ul class="nav__list">
  <li class="nav__item"></li>
</ul>
```

```css
/* Wrong */
.nav__list .nav__item {
  padding: 0;
}

/* Correct */
.nav__item {
  padding: 0;
}
```

</details>
<details>
  <summary>Styling an Element Depending on its Context</summary>

> Styles of an element **must not** depend on the state of another element.
> **BUT** styling can depend on the state of the block.

```html
<ul class="nav__list nav__list--active">
  <li class="nav__item"></li>
</ul>
```

```css
/* Wrong */
.nav__list--active .nav__item {
  padding: 0;
}

/* Correct */
.nav--active .nav__link { /* Can be styled based on the state of the block */
  padding: 0;
}

.nav:hover .nav__link {
  padding: 0;
}
```

```html
<nav class="nav nav--active">
  <a class="nav__link" href="#">1</a>
</nav>
```

</details>
<details>
  <summary>Increasing an Element Specificity</summary>

> You **must not** add the block selector to an element selector not to increase specificity.
> Element **must** always be placed inside its block in HTML.

```html
<nav class="nav">
  <ul class="nav__list">...</ul>
</nav>
```

```css
/* Wrong */
.nav .nav__list {
  padding: 0;
}

/* Correct */
.nav__list {
  padding: 0;
}
```

</details>
<details>
  <summary>Increasing Modifier Specificity</summary>

> You **must not** use the main class together with a modifier in a selector not to increase specificity.
> Modifier **must** always be added in addition to the main class in CSS in HTML.

```css
/* Wrong */
.burger-menu.burger-menu--active {
  background-color: transparent;
}

/* Correct */
.burger-menu--active {
  background-color: transparent;
}
```

</details>
<details>
  <summary>Styling a Block in the Context of Another Block</summary>

> The styles of a block **must not** depend on where it is located.

```html
<div class="parent">
  <div class="child"></div>
</div>
```

```css
/* Wrong */
.parent .child {
  margin-bottom: 10px;
}

/* Correct */
.parent__element { /* use mix */
  margin-bottom: 10px;
}
```

```html
<div class="parent">
  <div class="child parent__element"></div>
</div>
```

</details>
<details>
  <summary>Setting the Block's External Geometry or Positioning</summary>

> A block **must not** set its position or have margins.

```html
<div class="parent">
  <div class="child">...</div>
</div>
```

```css
/* Wrong */
.child {
  position: absolute;
  top: 0;
  margin: 10px;
  padding: 10px;
}

/* Correct */
.parent__element { /* use mix */
  position: absolute;
  top: 0;
  margin: 10px;
}

.child {
  padding: 10px;
}
```

```html
<div class="parent">
  <div class="child parent__element">...</div>
</div>
```
</details>
