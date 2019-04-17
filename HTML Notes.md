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