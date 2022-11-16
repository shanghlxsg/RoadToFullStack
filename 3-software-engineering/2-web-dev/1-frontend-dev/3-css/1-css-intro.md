# CSS basics

Source: <https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics>

* CSS (Cascading Style Sheets) is the code that styles web content.
  * Like HTML, CSS is not a programming language, nor a markup language.
  * CSS acts as an extension to HTML (or other supported file types) and does nothing on its own without a target document.

* A typical web page comprises of a HTML file `index.html` and a CSS file `style.css` (stored in a subdirectory `styles`).
* The `styles.css` CSS file must be linked from the `index.html` HTML file with the element:

  ```HTML
  <html>
    <head>
      <meta ...>
        <!-- link CSS here -->
        <link rel="stylesheet"
              href="styles/style.css">
    </head>
    <body>...</body>
  </html>
  ```

## CSS rulesets

* Define the styling properties of a HTML element using a CSS **ruleset**:

  ```CSS
  selector {
    propertyName: propertyValue;
  }

  p {
    color: red;
    /* multiple rules */
    width: 500px;
    border: 1px solid black;
  }
  ```

* Define the same ruleset for multiple HTML elements:

  ```CSS
  p, li, h1 {
    color: red;
  }
  ```

## CSS selectors

* CSS selectors are used to target the HTML elements that needs to be styled. A wide variety of CSS selectors are available for precision when selecting elements to style:
  * CSS selectors based on HTML element type, class, and ID:

    ```CSS
    /* <h1 class="className" id="myHeader">...</h1> */

    /* element selector */
    h1 { }

    /* element class selector */
    .className { }

    /* element ID selector*/
    #myHeader { }

    /* specific attribute selector */
    h1[class], h1[id] { }

    /* particular value of specific attribute selector */
    a[href="https:example/com"] { }
    ```

  * CSS selectors based on pseudo-classes and pseudo-elements:

    ```CSS

## Fonts and texts

* To import fonts for use with the web page, one method is to link a [Google Fonts API](https://fonts.google.com) in `index.html`:

  ```HTML
  <html>
    <head>
      <meta ...>
        <link rel="stylesheet"
              href="styles/style.css">
        <!-- link Google Font here -->
        <link rel="stylesheet"
              href="https://fonts.googleapis.com/css?family=fontName1|font+Name2>
    </head>
    <body>...</body>
  </html>
  ```

* Then, in the CSS file, define the font family for the specific selector. Generally, always list at least one fallback web-safe font such as `serif` or `sans-serif` to avoid unexpected errors.

  ```CSS
  html {
    font-size: 10px;
    font-family: "Font Name", serif;
  }
  ```

* To further format the text for each selector:

  ```CSS
  h1 {
    font-size: 60px;
    text-align: center;
  }

  p, li {
    font-size: 16px;
    line-height: 2;
    letter-spacing: 1px;
  }
  ```

## The box model

* CSS layout is mostly based on the box model. Each box taking up space on the web page has properties such as:
  * `padding` is the space around the content.
  * `border` is the solid line just outside the padding.
  * `margin` is the space around the outside of the border.

* Other typical selector properties include:
  * `width` of an element.
  * `background-colour` behind an element's content and padding.
  * `color` of an element's content.
  * `text-shadow` sets a drop shadow on element's text content.
  * `display` sets the display mode of an element.
