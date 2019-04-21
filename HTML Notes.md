# HTML Notes

This note is written in Markdown with the support of Typora.

## Basics

### Element

![img](https://mdn.mozillademos.org/files/9347/grumpy-cat-small.png)

#### Block and Inline Element

There are two important categories of elements in HTML: Block and Inline

**Block**: The Content will appear on a new line, and other contents following the element will also appear on a new line.

**Inline**: Doesn't behave like that, no paragraph change will happen.

#### Empty(void) elements

Not all elements follow the above pattern of opening tag, content, closing tag. Some elements consist only of a single tag, which is usually used to insert/embed something in the document at the place it is included.  E.g.  `<img>`

#### Attributes

![&amp;amp;lt;p class="editor-note">My cat is very grumpy&amp;amp;lt;/p>](https://mdn.mozillademos.org/files/9345/grumpy-cat-attribute-small.png)

E.g.: `<p>A link to my <a href="https://www.mozilla.org/" title="The Mozilla homepage" target="_blank">favorite website</a>.</p>`

+ Where `<a>` stands for anchor.
+ Always include the (double) quotes.

#### Boolean attributes

Some attributes are boolean, so if you declare it, you don't need to specify the value, only the attribute name gonna do.

### Anatomy of HTML file

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My test page</title>
  </head>
  <body>
    <p>This is my page</p>
  </body>
</html>
```

1. `<!DOCTYPE html>`: Is the shortest string of characters that counts as a valid doctype; that's all you really need to know.
2. `<html></html>`: This element wraps all the content on the entire page, and is sometimes known as the root element.
3. `<head></head>`:This element acts as a container for all the stuff you want to include on the HTML page that *isn't* the content you are showing to your page's viewers. This includes things like keywords and a page description that you want to appear in search results, CSS to style our content, character set declarations, and more. You'll learn more about this in the next article in the series.
4. `<meta charset="utf-8">`: This element sets the character set your document should use to UTF-8, which includes most characters from the vast majority of human written languages. Essentially it can now handle any textual content you might put on it. There is no reason not to set this, and it can help avoid some problems later.
5. `<title></title>`:  This sets the title of your page, which is the title that appears in the browser tab the page is loaded in, and is used to describe the page when you bookmark/favorite it.
6. `<body></body>`: This contains *all* the content that you want to show to web users when they visit your page, whether that's text, images, videos, games, playable audio tracks, or whatever else.
7. Comments: `<!-- Comment Body -->`

### Head

The head's content is not displayed on the page. Instead, the head's job is to contain metadata about the document. 

#### Metadata

+ Many `<meta>` elements include `name` and `content` attributes:

  - `name` specifies the type of meta element it is; what type of information it contains.

  - `content` specifies the actual meta content.

    E.g.: 

    ```html
    <meta name="description" content="The MDN Web Docs Learning Area aims to...">
    ```

+ Some of the metadata types are universal for all sites, which is part of the HTML standard, like the "description" shown above. But there's still a lot of types created by certain websites, and they can be analyzed specifically by those sites. 

  e.g. 

  ``<meta name="twitter:title" content="Mozilla Developer Network">``

  This code will add a title to the share message displayed in twitter communications.

+ Understand how favicon works and be aware that there're more choices nowadays for choosing the icons which can fit into different types of devices.

+ link rel, rel is "relation"

### CSS and JS

  The def.s of css and js should be mastered. The two are most commonly applied to HTML via `<link>`element and the `<script>` element, respectively.

+ The `<script>` element does not have to go in the head; in fact, often it is better to put it at the bottom of the document body (just before the closing `</body>` tag), to make sure that all the HTML content has been read by the browser before it tries to apply JavaScript to it
+ The `<script>` element may look like an empty element, but it's not, and so needs a closing tag. Instead of pointing to an external script file, you can also choose to put your script inside the `<script>` element. Inversely, the link element is a typical empty element.

### The document language

Due to various practical reasons which can be imagined, we should set the default language of the document, which is achieved by adding an attribute to the first `<html>` tag:

```html
<html lang="en-US">
```

We can also set language to a specific portion of the document, and do many other manipulations. Just refer to [Language tags in HTML and XML](https://www.w3.org/International/articles/language-tags/).

### Text Formatting

#### Semantics

Def.: The meaning or relationship of meanings of a sign or set of signs

**One thing worth Stressing**: All the semantics of the components of HTML design, for example, the h1 heading per se, should be respected. One reason is that many sites like search engines will use the h1 tag as an important reference. Therefore, you obviously can use CSS to restyle the h1 and not using it as Biggest header, it's not recommended.

**Conclusion**: Use the relevant HTML element for the job.

#### List

+ ordered `<ol></ol>` and unordered `<ul></ul>`

+ Each item `<li>xxx</li>`

+ Nesting

+ ```html
  Description lists:
  <dl>
    <dt>soliloquy</dt>
    <dd>In drama, where a character speaks to themselves, representing their inner thoughts or feelings and in the process relaying them to the audience (but not to other characters.)</dd>
  </dl>
  ```

#### Quotation

```html
<blockquote cite="">
    block quote
</blockquote>

<q cite="">inline quote</q>
```

#### Citation

```html
<cite>MDN blockquote page</cite>
```

#### Abbreviation

```html
<abbr title="Hypertext Markup Language">HTML</abbr>
```

#### Others

`<code>`: For marking up generic pieces of computer code. 

`<pre>`: For retaining whitespace (generally code blocks) — if you use indentation or excess whitespace inside your text, browsers will ignore it and you will not see it on your rendered page. If you wrap the text in `<pre></pre>` tags however, your whitespace will be rendered identically to how you see it in your text editor. 

`<var>`: For specifically marking up variable names. 

`<kbd>`: For marking up keyboard (and other types of) input entered into the computer. 

`<samp>`: For marking up the output of a computer program.

The `<time>` element allows you to attach an unambiguous, machine-readable time/date for this purpose.

`<hr>`: make a horizontal line

`<br>`: **Break into a new line**

### Various inline formating

Italics, emph, strong... Just consult the cheating sheet！

### Hypertext Reference

You can put everything into the anchor elements to attach a hypertext reference to it.

```html
<a href="https://www.mozilla.org/en-US/">
    <!-- You can plug in even block level elements into this -->
  <img src="mozilla-image.png" alt="mozilla logo that links to the mozilla homepage">
</a>
```

+ Inside web page hyper reference:

  ```html
  <p>Visit my <a href="projects/index.html">project homepage</a>.</p>
  ```

The directory navigator are same as linux file system, meaning .. . are all useful.

+ Link to fragments:

  It is possible to link to a specific part of an HTML document (known as a **document fragment**), rather than just to the top of the document. To do this you first have to assign an `id` attribute to the element you want to link to. It normally makes sense to link to a specific heading, so this would look something like the following:

  ```html
  <h2 id="Mailing_address">Mailing address</h2>
  ```

  Then to link to that specific `id`, you'd include it at the end of the URL, preceded by a hash/pound symbol, for example:

  ```html
  <p>Want to write us a letter? Use our <a href="contacts.html#Mailing_address">mailing address</a>.</p>
  ```

  You can even use the document fragment reference on its own to link to *another part of the same document*:

  ```html
  <p>The <a href="#Mailing_address">company mailing address</a> can be found at the bottom of this page.</p>
  ```

+ Absolute versus relative URLs:

  The URL starting from the root way down to the file is absolute;

  The URL which is not complete and depends on the current directory is relative.

+ **Good** link text: [Download Firefox](https://firefox.com/)/**Bad** link text: [Click here](https://firefox.com/) to download Firefox

+ Use relative links wherever possible

+ Use words to avoid giving the users unexpected responses:

  ```html
  <p><a href="http://www.example.com/large-report.pdf">
    Download the sales report (PDF, 10MB)
  </a></p>
  
  <p><a href="http://www.example.com/video-stream/" target="_blank">
    Watch the video (stream opens in separate tab, HD quality)
  </a></p>
  
  <p><a href="http://www.example.com/car-game">
    Play the car game (requires Flash)
  </a></p>
  ```

+ Use `download` attribute to specify default fine save name

### Web site structure

AGAIN, the semantic matters(we'll see it more after applying CSS), so we need to show the semantic by using different mark-ups. 

Wrappers **couldn't be used alone**, they are just to wrap certain elements.

1. header `<header>`

2. navigation bar `<nav>`

3. main content `<main>`, subsections `<article>``<section>``<div>`

4. sidebar `<aside>` often in the `<main>`

5. footer `<footer>`
6. ![a simple website structure example featuring a main heading, navigation menu, main content, side bar, and footer.](https://mdn.mozillademos.org/files/12417/sample-website.png)

**Notice**:

+ `<header>` can be used more than on the h1 place, actually, it can mark out any subtitles of a certain section or articles.

#### Non-semantic wrappers

When no semantic wrapper can be found, just use this and add attributes `class` to make the CSS afterwards work.

+ inline: `<span>`
+ block level: `<div>`

E.g.: A shopping cart in an e-commerce site. It may not fit in any semantic contexts, but are indeed combined together.

**Warning**: Divs are so convenient to use that it's easy to use them too much. As they carry no semantic value, they just clutter your HTML code. Take care to use them only when there is no better semantic solution and try to reduce their usage to the minimum otherwise you'll have a hard time updating and maintaining your documents.

### Debugging

Use explorer's inspection tools -- DOM to debug.

**CONTENTS NEED TO BE WENT OVER**

## Reminders

+ Be careful with the reserved letters:

| Literal character | Character reference equivalent |
| ----------------- | ------------------------------ |
| <                 | `&lt;`                         |
| >                 | `&gt;`                         |
| "                 | `&quot;`                       |
| '                 | `&apos;`                       |
| &                 | `&amp;`                        |

+ Metadata: It's data about data.