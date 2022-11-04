# HTML metadata

* The `<head>` of a HTML document is the part that is not displayed in the web browser when the page is loaded, as opposed to the `<body>` of the HTML document that is displayed on the page when loaded in a browser.
* The purpose of the `<head>` is to contain metadata `<meta>` about the document.

## HTML &lt;title&gt;

* The `<title>` element is metadata that represents the title of the overall HTML document (not to be confused with `<h1>` element in the `<body>`).
* The contents of the `<title>` element will only be:
  * Shown as the name of the browser tab.
  * Autofills as the *suggested* name of the bookmark of the page.
  * Used on search engine result pages.

## HTML &lt;meta&gt;data

* Metadata is data that decribes data, and HTML officially uses `<meta>` element to add metadata to a document.
* A lot of features on websites are proprietary creations designed to provide certain sites with specific pieces of information they can use through various metadata protocols (e.g., `Open Graph Data` by Facebook and `Twitter Cards` by Twitter).

```HTML
<!-- specify document's character encoding -->
<!-- utf-8 is a universal character set for almost every human langauge -->
<meta charset="utf-8">

<!-- author and description -->
<meta name="author" content="John Doe">
<meta name="description" content="This is a HTML metadata element guide.">
<!-- description metadata are also used on search engine result pages -->
```

## HTML custom icons

* To further enrich a site design, references to custom icons can be added to the metadata and the icons will be displayed in certain contexts.
  * `favicon` is the most common custom icon made of a 16px square icon used in multiple places like the browser tab and bookmarks panel.
    * It is saved in the same directory as the site's index page.
    * It can be saved in the `.gif` or `.png` format, but the `.ico` format ensures backwards compatibility as far back as IE6.
  * Other icon types can be used in modern HTML, such as high definition icons for Apple devices when saved on the device's homepage.

```HTML
<!-- most common custom icon -->
<link rel="icon" href="favicon.ico" type="image/x-icon">

<!-- iPad and iPhone square icons in sizes 144px, 114px, 72px, and 57px -->
<link rel="apple-touch-icon-precomposed" [sizes="144x144"] href="reference/link.png">
```

## HTML with CSS and JavaScript

* Apply CSS and JavaScript to HTML using the `<link>` and `<script>` elements respectively.
* The `<link>` element should include the `rel="stylesheet"` and `href` attributes.
* The `<script>` element should include the `src` attribute (similar to `href` in `<link>`), and the `defer` attribute so that the HTML page does not load the JavaScript until the page has finished parsing the HTML.
  * The `<script>` element is not an empty element so it needs a closing tag.
  * Instead of pointing to an external script file, the JavaScript can also be placed inside as the `<script>` element contents.

```HTML
<link rel="stylesheet" href="styles.css">
<script src="script.js" defer></script>

```

## HTML document primary langauge

* The language of a page can be set with the `lang` attribute in the opening `<html>` tag.
* By setting the language, the HTML document will be indexed more efficiently by search engines.
* It is also useful for users with visual impairments using screen readers, to ensure the pronunciation is given in the correct langauge.
* Subsections of a document can also be set to a different language if required using the `<span>` nested element with the `lang` attribute.
* The language codes are defined by the [ISO 639-1](https://en.wikipedia.org/wiki/ISO_639-1) standard.

```HTML
<html lang="en-US">
    ...
    <body>
        <p>Japanese example: <span lang="ja">ご飯が熱い。</span>.</p>
    </body>
</html>
```
