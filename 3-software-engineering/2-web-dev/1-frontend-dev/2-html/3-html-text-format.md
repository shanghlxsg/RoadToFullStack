# HTML text format

## Basic text formatting

### HTML headers and paragraphs

- Headers `<h1>` through `<h6>` provides hierachy to any text document (title, chapter, section, sub-section, etc.).
- Paragraphs `<p>` each denote a block of text. Content wrapped in subsequent elements will start on a newline.
- Use header and paragraphs to implement **structural hieracy** and **semantics**.

### HTML lists

```html
<!-- Unordered list -->
<ul>
    <li>Point A</li>
    <li>Point B</li>
</ul>

<!--- Ordered list -->
<ol>
    <li>Point 1</li>
    <li>Point 2</li>
</ol>
```

- Items in a list are wrapped with `<li>` element.
- Unordered lists (bullet points) have `<li>` elements wrapped with the `<ul>` element.
- Ordered lists (numbered points) have `<li>` elements wrapped with the `<ol>` element.
- Lists can be nested.

### HTML text emphasis

- Text emphasis elements are inline elements.
- Bold texts are wrapped with the `<strong>` element.
- Italic texts are wrapped with the `<em>` element.
- Highlighted texts are wrapped with the `<mark>` element.
- All other text emphasis or style shall be implemented using CSS and the `<span>` element with an appropriate `class` attribute.

*Note that the HTML4-deprecated `<b>`, `<i>` and `<u>` elements are redefined in HTML5 with new (confusing) semantic roles. Avoid using these elements in their deprecated sense.*

## Advanced text formatting

### HTML description lists

