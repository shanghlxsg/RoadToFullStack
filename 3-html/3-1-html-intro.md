# HTML basics

Source: <https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics>

* HTML (HyperText Markup Language) is the most basic building block of the web.
  * HTML uses `markup` to annotate text, images, and other content for display in the web browser. which includes special `elements` such as `<head>`, `<title>`, etc.
  * HTML element is identified by the use of tags `<` and `>`.
  * The convention and recommended practice is to write tags in lowercase.

## HTML elements

* A HTML element encloses its contents with an opening tag and closing tag.
  * Opening tag `<elementName>`.
  * Contents `element contents`.
  * Closing tag `</elementName>`.

* There are two key categories of elements in HTML:
  * `Block-level elements` form a visible block on the page. Any content before and after a block-level element appear on a new line.
  * `Inline elements` are contained within block-level elements, surrounding only small parts of the contents. Inline elements will not cause a new line to appear.

### Nesting HTML elements

* In `nested elements`, the child element must always be closed before the parent element.

```HTML
<p>This is a <desc>paragraph</desc>.</p>

<!--with proper styling-->

<p>
  This is a 
  <desc>
    paragraph
  </desc>
  .
</p>
```

### Empty HTML elements

* Some elements have no content and are called `empty elements`. Empty elements do not require closing tags (see [HTML image elements](#html-image-elements))

### HTML image elements

```HTML
<img src="file/path.type" alt="alt text">
```

* The `src` attribute locates the source path to the specified image file.
* The `alt` attribute contains the description text for users who cannot see the image (see [guide on accessibility](https://developer.mozilla.org/en-US/docs/Learn/Accessibility)).

### HTML text elements

#### HTML heading elements

* HTML allows for up to 6 heading levels, using the element names `<h1></h1>` through `<h6></h6>`.

```HTML
<h1>Main title</h1>
<h2>Top level heading</h2>
<h3>Subheading</h3>
<h4>Sub-subheading</h4>
```

#### HTML paragraph elements

* `<p></p>` elements contains paragraphs of texts, used frequently when marking up regular text content, normally placed below the `img` elements.

```HTML
<p>This is a single paragraph</p>
```

#### HTML list elements

* `<ul></ul>` elements define unordered lists.
* `<ol></ol>` elements define ordered lists.
* `<li></li>` (list item) elements are nested within ordered/unordered list elements. Each element defines a single bullet/numbering.

```HTML
<p>The elements of a HTML list are:</p>

<ol>
  <li>Ordered lists.</li>
  <li>Unordered lists.</li>
</ol>
```

### HTML anchor elements (links)

* Links are defined by anchor elements `<a></a>` that require the `href` (hypertext reference) attribute specifying the link.
* Links should include the specific protocol (`http://` or `https://`) to prevent unexpected errors.

```HTML
<a href="https://www.google.com">Google homepage</a>
```

* Anchor element attributes:
  * `href="<URL>"` specifies the link target.
  * `title="Text here."` specifies the tooltip text when a cursor hovers over the anchor element.
  * `target="_blank"` specifies the browsing context used to display the link.

## HTML attributes

* The `attributes` of a HTML element can be defined in its opening tag.
  * Attributes contain extra information about the element that should not appear in the actual content.
  * Opening tag `<p attributeName="attributeValue">`.
  * The `attributeName` attribute assigns a non-unique identifier to the element that can be used to target it (with style information and other things).
  * An attribute should always have:
    1. A space between it and the element name, or the previous attribute.
    2. The `attributeName` followed with `=` character.
    3. The `attributeValue` wrapped with `"` characters.

```HTML
<p class="editor-note">This is a paragraph</p>
```

### Boolean attributes

* Boolean attributes are attributes written without values as they can only have a single value that is usually the same as the attribute's name. Hence, the value of the boolean attribute is implied by its name.
* E.g., the `disabled` attribute can be written as `disabled` or `disabled="disabled"`.

```HTML
<input type="text" disabled="disabled">
<!-- is the same as -->
<input type="text" disabled>
<!-- prevents end user from entering text into the input box -->

<input type="text">
<!-- end user is allowed to enter text into the input box -->
```

### Best practices for HTML attributes

* While there are some cases where the attribute name does not need to be wrapped in quotes, it will more than likely cause unexpected errors. Hence, it is always recommended to wrap attribute names with quotes.
* Single or double quotes? It is purely a matter of style and has no functional difference between `'` and `"` as long as only one is consistently used throughout the project.
  * To escape the single/double quotes being interpreted as code, use [special characters](#special-characters-in-html).

## HTML documents

* The basic structure of a complete HTML document `index.html` requires the following elements:
  * `<!DOCTYPE html>` doctype is needed, in simple terms, to make sure the HTML document behaves correctly.
  * `<html></html>` wraps all the content on the entire page and is also known as the root (top-level) element.
  * `<head></head>` acts as a container for all machine-readadable information (metadata) that *is not* the visible contents.
  * `<meta charset="utf-8">` element sets the character set of the document. `UTF-8` includes most characters from the vast majority of written .
  * `<meta name="viewport" content="width=device-width">` element ensure the page renders at the width of the viewport (prevents mobile browsers from rendering pages wider than viewport and then shrinking them down).
  * `<title></title>` element sets the title of the page.
  * `<body></body>` element contains *all* the content that needs to be shown to the user, whether it is text, images, videos, games, audio, etc.

```HTML
<!DOCTYPE html>
<html lang="en-US">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>My test page</title>
  </head>
  <body>
    <img src="images/firefox-icon.png" alt="My test image">
  </body>
</html>
```

## Whitespace in HTML

* All whitespace strings, regardless of length, will be reduced to a single character by the HTML parser.

## Special characters in HTML

* To include special characters in the HTML text and avoid having the HTML parser interprete as code, the character reference equivalent is required.
  * `<` is referenced by `&lt;` (less than).
  * `>` is referenced by `&gt;` (greater than).
  * `"` is referenced by `&quot;` (quotation).
  * `'` is referenced by `&apos;` (apostrophe).
  * `&` is referenced by `&amp;` (ampersand).

## HTML comments

* HTML comments are wrapped with special markers `<!--` and `-->`.
