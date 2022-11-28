# HTML `<head>`

- Stores metadata as the content of the `<head>` block element.
- The contents within the block element are **not** displayed on the web page.

## HTML `<title>`

- Defines the document's title that is shown in browser.
- Plain text only, nested inline elements are ignored.

## HTML `<meta>`

```html
<!-- utf-8 is a universal character set for almost every human langauge -->
<meta charset="utf-8" />
<meta http-equiv="refresh" content="3;url=https://www.mozilla.org" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<meta name="author" content="..." />
<meta
  name="description"
  content="..." />
```

- Represents metadata that cannot be represented by other HTML metadata elements.
- Void element containing one of the following attributes:
  - `charset` attribute declares the character encoding for the document.
  - `content` attribute contains the value for `http-equiv` or `name` attributes (forming a key-value pair).
  - `http-equiv` attribute defines a pragma directive. See [allowed values](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta#attr-http-equiv).
  - `name` attribute provides document-level metadata. See HTML standard [metadata names](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta/name#standard_metadata_names_defined_in_the_html_specification).
    - Properly specified metadata can improve [SEO](https://developer.mozilla.org/en-US/docs/Glossary/SEO)).

## HTML custom icons

```html
<link rel="icon" href="favicon.ico" />

<!-- (Optional) iPad and iPhone square icons in sizes 144px, 114px, 72px, and 57px -->
<link rel="apple-touch-icon-precomposed" [sizes="144x144"] href="reference/link.png">
```

- Favicon (favourites icon) is a square icon used by browsers alongside the title of the web page.
- Most commonly stored as `.ico`, while most browsers also support common formats like `.gif` or `.png`.

## HTML with CSS and JavaScript

```html
<link rel="stylesheet" href="styles.css">
<script src="script.js" defer></script>
```

- CSS is linked to the HTML document using `<link>` element with `rel="stylesheet"` attribute.
- JavaScript is linked to the HTML document using `<script>` element with `src="script.js"` attribute.
  - The `defer` attribute instructs the browser to load the script *after* the page has finished parsing the HTML.

## HTML content langauge

```HTML
<html lang="en-US">
    <head>
      <!-- Some metadata here -->
    </head>
    <body>
        <p>Japanese example: <span lang="ja-JP">ご飯が熱い。</span>.</p>
    </body>
</html>
```

- The primary langauge is set using the `lang="en"` attribute in the `<html>` element's opening tag.
- Within a block element, you may specify an alternate language using the `<span>` element with `lang="ja"` attribute.

### Global attribute `lang`

- Helps define the language of an element.
- The attribute value is typically written as 2-letter langauge code and 2-letter region code.
- See comprehensive list of [accepted values](https://www.techonthenet.com/js/language_tags.php).
