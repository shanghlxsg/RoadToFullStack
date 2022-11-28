# Introduction to HTML

[Source](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Getting_started).

HTML (HyperText Markup Language) tells web browsers how to structure the web page via a series of `elements` enclosed in `tags`.

## Anatomy of HTML elements

```html
<p>Contents of an element goes here.</p>
```

- The opening tag `<p>` indicates the name and type of HTML element.
- The closing tag `</p>` closes the HTML element.
- The content is the text enclosed by `<p>` and `</p>`.

### Attributes

```html
<div attribute="attribute-name">Content.</div>
```

- Optional.
- Contains extra information about the element.
- [List of element attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes#attribute_list) and their corresponding elements.

### Block & inline elements

*Before proceeding, take note that HTML5 uses [content categories](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories) instead of block-level/inline elements categorisation.*

#### Block elements

```html
<h1>Block-level element.</h1>
<p>This paragraph will appear in a new line.</p>
<div>Generic containers are also block-level.</div>
```

- Block-level elements form a visible block on a page. Any subsequent block-level elements appear in a new line.
- [List of block-level elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements#elements).

#### Inline elements

```html
<p><strong>Bold</strong> or <em>italic</em> elements are inline.</p>
```

- Inline elements (contained within block-level elements) appears in the same block.
- [List of inline elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements#list_of_inline_elements)

### Void elements

```html
<img
    src="https://picsum.photos"
    alt="Lorem Picsum"
/>
```

- Filled with element attributes.
- Does not have content.
- Only a single tag is required for the element.

### Nesting elements

#### Nested block elements

```html
<div>
    <header>
        <img src={logo} />
        <p>
            Nested block elements.
        </p>
    </header>
</div>
```

#### Nested inline elements

```html
<p>Text in <strong>bold and <em>bold-italics</em></strong>.</p>
```

## Anatomy of a HTML document

```html
<!DOCTYPE html>
<html lang="en-US">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>My test page</title>
  </head>
  <body>
    <img src="images/firefox-icon.png" alt="My test image" />
  </body>
</html>
```

- `<!DOCTYPE html>` is required to declare the document as HTML.
- `<html>` element wraps the entire content of the page.
- `<head>` element contains all the metadata of the page (everything that is not the content).
- `<meta>` element represents metadata that cannot be represented by other meta-related elements.
- `<title>` element sets the title of the page.
- `<body>` element contains all the content that is displayed on the page.

### Whitespace in HTML documents

- HTML parser reduces all whitespace to a single space when rendering the code.
- Feel free to use as much whitespace characters as possible to **improve code readability**.

### Entity references in HTML

- Since characters such as `< > " ' &` are parsed as code, character references must be used to display them as actual text.

    | Literal | Reference |
    |---------|-----------|
    | <       | `&lt;`    |
    | >       | `&gt;`    |
    | "       | `&quot;`  |
    | '       | `&apos;`  |
    | &       | `&amp;`   |

### Comments in HTML

```html
<!-- Comment in HTML within this tag -->
```
