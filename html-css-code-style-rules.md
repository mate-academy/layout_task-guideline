1. [STYLE] - Don't set fixed container size. Let the content size dictate it.


2. [STYLES] - Get used to style all elements using classes. And don't increase
selectors specificity unless completely necessary
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


3. [CODE STYLE] - Don't use simple tag names or specific styles in class names.
Exception - specific semantic tags, like `header`, `nav`, `footer` etc. Try to
describe the content of the tag.
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


4. [STYLES] - Remember to use fallback fonts - alternative font-family in case the main one doesn't work [like this](https://www.w3schools.com/cssref/pr_font_font-family.asp)


5. [CODE STYLE] - Keep your code line length below 80. It’s not only historical
tradition, but also allows your code to fit into one standard screen without
horizontal scroll. But do not break the line if it cannot be broken (ex., long links).


6. [CODE STYLE] - Remember about correct indentation between parent and child
elements. Each level of nesting, including text, contained inside the element,
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


7. [CODE STYLE] - Don't use spaces in links. Have you seen any link with literal
space in it on the Internet? Remember, anchor links start with `#`.


8. [CODE STYLE] - Make sure you have `alt` attribute for images, they must be
present
([find out more](https://osric.com/chris/accidental-developer/2012/01/when-should-alt-text-be-blank/)
and
[even more](https://9clouds.com/blog/the-importance-of-alt-attributes-aka-alt-text/))



9. [CODE KNOWLEDGE] - Don't use `*` selector for zeroing out your margins or paddings. It's still inefficient for browser to read your web document



10. [STYLES] - Remember that links should have `cursor: pointer` and clickable
zone on 100% of header height


11. [CODE STYLE] - If the HTML-element has long attribute values or number of
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


12. [CODE STYLE] - Add empty lines between multiline sibling blocks of HTML.
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


13. [CODE STYLE] - If several selectors MUST always have the same styles, group them using `,` to prevent accidental out ot sync in future
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