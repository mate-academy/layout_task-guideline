# Code Style Best Practices

[HTML](#HTML) 
[CSS](#CSS) 
---

## HTML

### Correct class naming
  - Don't use simple tag names or specific styles in class names.
  Exception - specific semantic tags, like `header`, `nav`, `footer` etc.
  Try to describe the content of the tag.
    <details>
      <summary>BAD example</summary>

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
      <summary>GOOD example</summary>

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

### Line length
  - Keep your code line length below 80.
  It’s not only historical tradition, but also allows your code to fit into one standard screen,
  without horizontal scroll. But do not break the line if it cannot be broken (ex., long links).

### Indentation
  - Remember about correct indentation between parent and child elements.
  Each level of nesting, including text, contained inside the element,
  requires 2-space offset. Also blank line shouldn't be between parent and child elements.
    <details>
      <summary>BAD examples</summary>

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
      <summary>GOOD example</summary>

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

### Link
  - Don't use spaces in links. Have you seen any link with literal
  space in it on the Internet? Remember, anchor links start with `#`

### Alternative image text
  - Make sure you have `alt` attribute for images, they must be
  present ([find out more](https://osric.com/chris/accidental-developer/2012/01/when-should-alt-text-be-blank/) and [even more](https://9clouds.com/blog/the-importance-of-alt-attributes-aka-alt-text/))

### Attributes formatting
  - If the HTML-element has long attribute values or number of
  attributes is more than 2 - start each one, including the first, on the new
  line with 2-space indentation related to tag. Tag’s closing bracket should be
  on the same level as opening one.
    <details>
      <summary>BAD examples</summary>
      
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
      <summary>GOOD example</summary>

      ```html
      <input
        type="text" 
        name="surname" 
        id="surname"
        required
      >
      ```
    </details>

### Empty lines
  - Add empty lines between multiline sibling blocks of HTML.
  But don't add empty lines between parent and child elements
    <details>
      <summary>BAD example</summary>

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
      <summary>GOOD example</summary>

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

### BEM
  - Create a separate file per each BEM block styles that have the same name as the block
  - Make sure to follow BEM naming convention for complex modifiers: 
  `block-name--modifier-name--modifier-value`
  - Check your BEM structure using BEM-linter (`npm run lint`) and [this list](https://mate-academy.github.io/fe-program/css/typical-bem-mistakes-en)
  - Don't add external styles (positioning or margins) to BEM-blocks.
  Use mix where necessary and move all external styles under element selector.
    
    <details>
      <summary>BAD example</summary>

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
    </details>

    <details>
      <summary>GOOD example</summary>

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

### SEO
  - Use semantic tags like header, nav, main, footer, section, article, h2, p ...
  - `alt` atribute should describe the image if the image contains information (better description you have - better for you :))

    <details>
      <summary>REALLY BAD example</summary>

      ```html
      <img alt="image" />
      ```
    </details>

    <details>
      <summary>STILL BAD example</summary>

      ```html
      <img alt="phone" />
      ```
    </details>

    <details>
      <summary>GOOD example</summary>

      ```html
      <img alt="Samsung Galaxy S22 2022 8/128GB Green" />
      ```
    </details>

---

## CSS


### SASS
  - Check your import syntax. It's differs from plain CSS.
  - Use variables for the main values so that you'll be able to reuse them,
  and give them descriptive names.
  But don't overuse them, don't create variable for the value that's used just once.
  - Don't use SASS loops for styles that stay the same for all elements
  of the group, e.g. `display` or `position`.
  - Make use of SASS nesting - write pseudo-class, pseudo-element
  selectors inside general selector. As well as media queries.

    <details>
      <summary>BAD example</summary>

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

    <details>
      <summary>GOOD example</summary>

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

## Transition
  - Make sure to list all styles that you apply transition to.
  - Make sure to add transition style under general selector, not the
  one with `:hover` - this way transition will work smoothly both ways.

    <details>
      <summary>BAD example</summary>

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
    </details>

    <details>
      <summary>GOOD example</summary>

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

### Fixed size
  - Don't set fixed container size. Let the content size dictate it.

### Style using classes
  - Get used to style all elements using classes. 
  - Don't increase selectors specificity unless completely necessary

    <details>
      <summary>HTML example</summary>

      ```html
      <nav class="nav">  
        <ul class="nav__list">  
          ...  
        <ul>  
      </nav>  
      ```
    </details>
    <details>
      <summary>BAD CSS examples</summary>

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
    </details>
    <details>
      <summary>GOOD CSS example</summary>

      ```css
      .nav__list {
        list-style: none
      }
      ```
    </details>

### Fallback fonts
  - Remember to use fallback fonts - alternative font-family in case the main one doesn't work [like this](https://www.w3schools.com/cssref/pr_font_font-family.asp)

### Styles resetting
  - Don't use `*` selector for zeroing out your margins or paddings.
  It's still inefficient for browser to read your web document

### Clickable elements
  - Remember that all clickable elements should have `cursor: pointer`
  - Sometimes it's also good to create clickable area around element

### Simplified selectors
  - If several selectors MUST always have the same styles, group them using `,` to prevent accidental out ot sync in future
    <details>
      <summary>BAD example</summary>

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
    </details>

    <details>
      <summary>GOOD example</summary>

      ```css
      .block--1,
      .block--2,
      .block--3 {
        background-color: yellowgreen;
      }
      ```
    </details>

### Border on hover
  - Don't add new border to the element on hover. 
  Add default transparent border of the same width, and change its color on `:hover`

### Consistent margins and paddings
  - Be consistent with your margins.
  Add only top or bottom, don't add both.
