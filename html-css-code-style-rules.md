# Code Style Best Practices

[HTML](#HTML) 
[CSS](#CSS) 
---

## HTML

<details>
  <summary>Don't use simple tag names or specific styles in class names</summary>

  - Exception - specific semantic tags, like `header`, `nav`, `footer` etc.
  Try to describe the content of the tag.

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
</details>

<details>
  <summary>Keep your code line length below 80</summary>

  - It’s not only historical tradition, but also allows your code to fit into one standard screen, without horizontal scroll. 
  But do not break the line if it cannot be broken (ex., long links).
</details>

<details>
  <summary>Remember about correct indentation between parent and child elements</summary>

  - Each level of nesting, including text, contained inside the element, requires 2-space offset. 
  Also blank line shouldn't be between parent and child elements.

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
</details>

<details>
  <summary>Don't use spaces in links</summary>

  - Have you seen any link with literal space in it on the Internet?
  Remember, anchor links start with `#`
</details>

<details>
  <summary>Make sure to have `alt` attribute for images</summary>

  - They must be present ([find out more](https://osric.com/chris/accidental-developer/2012/01/when-should-alt-text-be-blank/) and [even more](https://9clouds.com/blog/the-importance-of-alt-attributes-aka-alt-text/))
</details>

<details>
  <summary>Keep your attributes correctly formatted</summary>

  - If the HTML-element has long attribute values or number of attributes is more than 2 - start each one,
  including the first, on the new line with 2-space indentation related to tag.
  Tag’s closing bracket should be on the same level as opening one.

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

  GOOD Example
  ```html
  <input
    type="text" 
    name="surname" 
    id="surname"
    required
  >
  ```
</details>

<details>
  <summary>Use camelCase for values of 'name' attribute</summary>

  - They should be valid as JavaScript object keys.
  It should not contain spaces, or other special characters.

  BAD Example
  ```html
  <input
    type="date" 
    name="date of birth" 
    id="dateOfBirth"
    required
  >
  ```

  GOOD Example
 ```html
  <input
    type="date" 
    name="dateOfBirth" 
    id="dateOfBirth"
    required
  >
  ```
</details>

<details>
  <summary>Add empty lines between multiline sibling blocks of HTML</summary>

  - But don't add them between parent and child elements

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
</details>

<details>
  <summary>BEM</summary>

  - Create a separate file per each BEM block styles that have the same name as the block
  - Make sure to follow BEM naming convention for complex modifiers: 
  `block-name--modifier-name--modifier-value`
  - Check your BEM structure using BEM-linter (`npm run lint`) and [this list](https://mate-academy.github.io/fe-program/css/typical-bem-mistakes-en)
  - Make sure to follow BEM naming convention

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

  - Don't add external styles (positioning or margins) to BEM-blocks.
  Use mix where necessary and move all external styles under element selector.

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


<details>
  <summary>Make use of semantic tags, attributes, etc.</summary>

  - Use semantic tags like header, nav, main, footer, section, article, h2, p ...
  - `alt` atribute should describe the image if the image contains information (better description you have - better for you :))

  REALLY BAD example
  ```html
  <img alt="image" />
  ```

  STILL BAD example
  ```html
  <img alt="phone" />
  ```

  GOOD example<
  ```html
  <img alt="Samsung Galaxy S22 2022 8/128GB Green" />
  ```
</details>

---

## CSS

<details>
  <summary>SASS</summary>

  - Check your import syntax. It's differs from plain CSS.
  - Use variables for the main values so that you'll be able to reuse them,
  and give them descriptive names.
  But don't overuse them, don't create variable for the value that's used just once.
  - Don't use SASS loops for styles that stay the same for all elements
  of the group, e.g. `display` or `position`.
  - Try to use different features - mixins etc - where it makes sense.
  - Make use of SASS nesting - write pseudo-class, pseudo-element
  selectors inside general selector. As well as media queries.

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
</details>

<details>
  <summary>Make sure to correctly set transition properties</summary>

  - List all styles that you apply transition to.
  - Add transition style under general selector, not the
  one with `:hover` - this way transition will work smoothly both ways.

  BAD Example
  ```scss
  .box {
    color: gray;

    &:hover {
      color: aquamarine;
      transform: scale(1.2);
      transition: 0.5s;
    }
  }
  ```
  GOOD Example
  ```scss
  .box {
    color: gray;
    transition: color 0.5s, transform 0.5s;

    &:hover {
      color: aquamarine;
      transform: scale(1.2);
    }
  }
  ```
</details>

<details>
  <summary>Don't set fixed container size</summary>

  - Let the content size dictate it.
</details>

<details>
  <summary>Get used to correct styling rules</summary>

  - Style all elements using classes. 
  - Don't increase selectors specificity unless completely necessary

  HTML Example
  ```html
  <nav class="nav">  
    <ul class="nav__list">  
      ...  
    <ul>  
  </nav>  
  ```

  BAD CSS Examples
  ```css
  ul {
    list-style: none
  }
  ```

  ```css
  nav ul {
    list-style: none
  }
  ```

  GOOD CSS Example
  ```css
  .nav__list {
    list-style: none
  }
  ```

  - If you have two or more similar elements with portions of similar styles with different values - use one
  of the elements as the basic case, and override necessary styles for other cases.
  Explanation: The point is not in the names of the classes, the point is: when there are several similar elements, ex., 2 inputs, for one we can give a class input, for example, and for the second - input input--small. We write all the styles for .input, but for .input-small we write only those styles that differ in design, and we need this second input to look a little different.
  Element with class .input without extra classes should also look like a full-fledged styled element.

  BAD Example
  ```html
  <!--index.html-->

  <img 
    class="icon-big"
    src="url(./logo.png)"
    alt="Company logo"
  >

  <img
    class="icon-small"
    src="url(./logo-small.png)"
    alt="Company small logo"
  >
  ```

  ```css
  /*styles.css*/

  .icon-big {
    position: absolute;
    top: 24px;
    left: 24px;
    display: block;
    width: 40px;
    height: 40px;
  }

  .icon-small {
    position: absolute;
    top: 16px;
    left: 16px;
    display: block;
    width: 32px;
    height: 32px;
  }
  ```

  GOOD Example
  ```html
  <!--index.html-->

  <img 
    class="icon" 
    src="url(./logo.png)" 
    alt="Company logo"
  >

  <img 
    class="icon icon--small"
    src="url(./logo-small.png)" 
    alt="Company small logo"
  >
  ```

  ```css
  /*styles.css*/

  .icon {
    position: absolute;
    top: 24px;
    left: 24px;
    display: block;
    width: 40px;
    height: 40px;
  }

  .icon--small {
    top: 16px;
    left: 16px;
    width: 32px;
    height: 32px;
  }
  ```
</details>

<details>
  <summary>Use fallback fonts</summary>

  - Fallback font - alternative font-family in case the main one doesn't work [like this](https://www.w3schools.com/cssref/pr_font_font-family.asp)
</details>

<details>
  <summary>Don't use * for resetting</summary>

  - Zeroing out your margins, paddings or other styles with '*' is not the best way to do it.
  It's still inefficient for browser to read your web document
</details>

<details>
  <summary>Apply correct styles to clickable elements</summary>

  - All clickable elements should have `cursor: pointer`
  - Sometimes it's also good to create clickable area around element
</details>

<details>
  <summary>Don't add new border to the element on hover</summary>

  - Add default transparent border of the same width, and change its color on `:hover`
</details>

<details>
  <summary>Be consistent with your margins.</summary>

  - Add only top or bottom, don't add both.
</details>

<details>
  <summary>Use simplfiied selectors when it's possible</summary>

  - If several selectors MUST always have the same styles, group them using `,` to prevent accidental out of sync in future

  BAD Example
  ```css
  .block--1 {
    background-color: yellowgreen;
  }

  .block--2 {
    background-color: yellowgreen;
  }

  .block--3 {
    background-color: yellowgreen;
  }
  ```

  GOOD Example
  ```css
  .block--1,
  .block--2,
  .block--3 {
    background-color: yellowgreen;
  }
  ```
</details>