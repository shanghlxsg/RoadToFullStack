# HTML hyperlinks

Hyperlinks (links) is a reference to any resource available from the point of access, both local (local paths) and online (URLs).

## Referencing (web) links

```html
<p>
    Visit
    <a
        href="https://www.google.com"
        title="The homepage of the internet">Google</a>
    for more.
</p>
```

- The `<a>` (anchor) element in the `<body>` block is similar to the `<link>` element used in the `<head>` block.
- The `href` attribute is used to specify the link/target.
- The `title` attribute is optional and contains additional information about the link.
- Almost **any** content can be made into a link (including block elements) by wrapping it with the `<a>` element.

## Referencing local files (document fragments)

```html
<h2 id="Chapter_X">Chapter X</h1>

<!-- Some content later -->
<p>
    Go to
    <a href="index.html#Chapter_X">Chapter X</a>
    for more information
</p>
```

- Reference a local file by specifying the file path and name.
- Reference a **section** of the document (document fragment) by assigning an `id` attribute to the target element and append the value of the `id` to the file path with a `#` (hash/pound symbol).

## Referencing download files

```html
<a
    href="https://download.somewhere.com/?product-version"
    download="file-name-when-downloaded.exe">
    Download product (version)
</a>
```

- Instruct the browser to initial the file download process using the `download` attribute in addition to the `href` attribute in the `<a>` element.

## Referencing emails

```html
<a href="mailto:someone@somewhere.com">Send email</a>

<!-- Set parameters for email template -->
<a href="mailto:someone@somewhere.com?cc=another@elsewhere.org&subject=Email%20subject&body=Insert%20body%20here">
    Send email with template
</a>
```

- Simply append `mailto:` to any email address in the `href` attribute to initiate sending an email (using the system's default email application).
- Set an email template by including it in the link parameters.
  - See API query [GET method](https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_and_retrieving_form_data#the_get_method).

## Best practices

```html

```

1. Always use absolute links/paths instead of relative links/paths.
   - Relative links and paths may change as the location of the root reference is relocated down the road.
2. Use clear, short and descriptive link wordings.

    ```html
    <!-- Good practice -->
    <p>
        <a
            href="https://download.somewhere.com/?product-version"
            download="file-name-when-downloaded.exe">
            Download product (version)
        </a>
    </p>

    <!-- Bad practice -->
    <p>
        <a
            href="https://download.somewhere.com/?product-version"
            download="file-name-when-downloaded.exe">
            Click here
        </a>
        to download
    </p>
    ```

3. Avoid using the same wordings for different links.
4. [Leave clear signposts](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Creating_hyperlinks#linking_to_non-html_resources_%E2%80%94_leave_clear_signposts) when linking to non-HTML resources.

```html

```
