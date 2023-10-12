# Code Style Best Practices

## HTML Formatting
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

## HTML Content

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

## CSS
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


## BEM

<details>
  <summary>Follow naming convention</summary>

  BAD Example
  ```html
  <div class="product__rating">
    <div class="product__stars stars--4">
      <div class="star"></div>
      <div class="star"></div>
      <div class="star"></div>
      <div class="star"></div>
      <div class="star"></div>
    </div>
  </div>
  ```

  GOOD Example
  ```html
  <div class="product__rating">
    <div class="product__stars stars stars--4">
      <div class="stars__star"></div>
      <div class="stars__star"></div>
      <div class="stars__star"></div>
      <div class="stars__star"></div>
      <div class="stars__star"></div>
    </div>
  </div>

  `stars--4` is a modifier of the `stars` block, but `stars` block does not exist in HTML;
  `star` is another block, stars should be the elements of the `stars` block
  ```
</details>

<details>
  <summary>Follow naming convention for complex modifiers</summary>

  - `block-name--modifier-name--modifier-value`
</details>

<details>
  <summary>Check your structure using linter</summary>

  - (`npm run lint`) and [this list](https://mate-academy.github.io/fe-program/css/typical-bem-mistakes-en)
</details>

<details>
  <summary>Create a separate file per each styles block</summary>

  - If styles block has the same name as BEM block - create separate file for it
</details>

<details>
  <summary>Don't add external styles (positioning or margins) to blocks</summary>

  - Use mix where necessary and move all external styles under element selector.

  BAD Example
  ```html
  <!--index.html-->
  <div class="container">
    <div class="card">
      ...
    </div>
  </div>
  ```

  ```css
  /*styles.css*/
  .card {
    margin: 48px 24px;
    font-size: 16px;
    background-color: purple;
  }
  ```

  GOOD Example
  ```html
  <!--index.html-->
  <div class="container">
    <div class="container__card card">
      ...
    </div>
  </div>
  ```

  ```css
  /*styles.css*/
  .container__card {
    margin: 48px 24px;
  }

  .card {
    font-size: 16px;
    background-color: purple;
  }
  ```
</details>

## SASS

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
