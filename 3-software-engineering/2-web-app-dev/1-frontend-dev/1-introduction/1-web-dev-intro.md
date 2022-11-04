# Introduction to the web

## Core technologies of the web

As mentioned in [JavaScript fundamentals](/2-javascript/2-1-js-fundamentals.md), the key elements that forms a website are:

* HTML
  * Responsible for contents of the web page (texts, images, buttons, etc.).

* CSS
  * Responsible for the presentation of the HTML contents (styling and laying out elements on the webpage).

* Javascript
  * The real programming langauge of the internet.

## Structure of a website

The most common structure of a website includes:

* `index.html` file in the parent project folder.
* `images` folder that will contain all the images used on the site.
* `styles` folder that will contain the CSS code used to style the contents on the site.
* `scripts` folder that will contain the JavaScript code used to add interactive functionality to the site.

## File paths

* To link to a target file in the *same* directory as the invoking HTML file, only the `filename.type` is required.
* To reference a file in a subdirectory, simply include the subdirectory path (including a forward slash `/`) in front of the target file path `subdirectory/sub-subdirectory/filename.type`.
* To link to a target file in the directory above the invoking HTML file, use `../` to nagivate one level higher.

## Publishing a website

* To have more control over content and website appearance, most users choose to buy web hosting services and a domain name:
  * `Web hosting services` rent file space on a hosting company's web server where the website files will be stored, providing website content to website visitors.
  * A `domain name` is the unique address to locate the website (e.g., `https://www.google.com` or `http://www.mozilla.org`). A domain name can be rented from a domain registrar for as long as required.
  * A `FTP` (file tranfer protocol) is also required to transfer the website files to the web hosting server.

* Alternatively, use online tools like `GitHub Pages` or `Google App Engine` to build and run websites and web applications.

## How the web works

* Computers connected to the internet are called `clients` and `servers`.
  * Clients send `requests` to servers.
  * Servers send `responses` to clients.

* In addition, the web also requires:
  * Internet connection.
  * `TCP/IP` (Transmission Control Protocol and Internet Protocol) - communication protocols that define how data should travel across the internet.
  * `DNS` (Domain Name System) - the address book for servers which the website is hosted on so that it can be located.
  * `HTTP` (HyperText Transfer Protocol) - an application protocol that defines a langauge for clients and servers to communicate.
  * `Component files` - a website is made of 2 main types of files:
    * `Code files` - HTML, CSS, and JavaScript files.
    * `Assets` - media and text content documents that do not affect the structure of the website.

* For a website to work:
  1. The browser (Firefox, Chrome, Edge, etc.) goes to the DNS server and finds the real address of the server that the target website is hosted on.
  2. The browser sends a HTTP request message to the server, requesting for a copy of the website to the client, sent over internet connection using TCP/IP.
  3. If the server approves the request, it will send a `200 OK` response message, followed by the website files in small chunks called `data packets`.
  4. The browser is responsible for assembling the data packets into a complete website.

* The order by which the data packets are parsed by the browser:
  1. The browser parses the HTML file first to get `<link>` and `<script>` element references.
  2. The browser generates an in-memory `DOM tree` from the parsed HTML.
  3. The browser generates an in-memory `CSSOM` structure from the parsed CSS.
  4. The browser compiles and executes the parsed JavaScripts.
  5. The browser has a complete set of instructions to display the page content on the client side.
