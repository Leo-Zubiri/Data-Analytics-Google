
> This repository was created to learn how to generate dynamic documentation with **docsify**. I only used some features I consider it useful to have a good documentation
>
> Also, I use this repo to take notes and store documents about a Google Data Analysis course that I'm taking.



<p width="100%" style="text-align: center;  font-size: 20px;font-weight: bold;         margin-top: 30px;
        margin-bottom: 50px;"> 
    <a 
        style="    color: #00FF17;"
        href="https://leo-zubiri.github.io/Data-Analytics-Google/"
    > 
    🚀 Visit Data Analytics Documentation 🚀
    </a>
</p>

# Docsify

[`A magical documentation site generator`](https://docsify.js.org/#/quickstart)

## SETUP

It is recommended to install `docsify-cli` globally, which helps initializing and previewing the website locally.

```bash
npm i docsify-cli -g
```

Then prepare a directory to store the documentation files:

```bash
docsify init ./docs
```

Run the local server with `docsify serve`. You can preview your site in your browser on `http://localhost:3000`.

```bash
docsify serve docs
```

## More Pages

Create more markdown files directly in docs or into more subdirectories:

We can set a link to a page:

```
![Page](/#/page)

![Page](/#/directory/page)
```

## Text Search

Edit index.html file and set next code respectively:

```html
  <script>
    window.$docsify = {

      search: 'auto', // default
  
      search: [
        '/',            // => /README.md
        '/guide',       // => /guide.md
        '/get-started', // => /get-started.md
        '/zh-cn/',      // => /zh-cn/README.md
      ],
  
      // complete configuration parameters
      search: {
        maxAge: 86400000, // Expiration time, the default one day
        paths: [], // or 'auto'
        placeholder: 'Type to search',
  
        // Localization
        placeholder: {
          '/zh-cn/': '搜索',
          '/': 'Type to search',
        },
  
        noData: 'No Results!',
  
        // Localization
        noData: {
          '/zh-cn/': '找不到结果',
          '/': 'No Results',
        },
  
        // Headline depth, 1 - 6
        depth: 2,
  
        hideOtherSidebarContent: false, // whether or not to hide other sidebar content
  
        // To avoid search index collision
        // between multiple websites under the same domain
        namespace: 'website-1',
  
        // Use different indexes for path prefixes (namespaces).
        // NOTE: Only works in 'auto' mode.
        //
        // When initialiazing an index, we look for the first path from the sidebar.
        // If it matches the prefix from the list, we switch to the corresponding index.
        pathNamespaces: ['/zh-cn', '/ru-ru', '/ru-ru/v1'],
  
        // You can provide a regexp to match prefixes. In this case,
        // the matching substring will be used to identify the index
        pathNamespaces: /^(\/(zh-cn|ru-ru))?(\/(v1|v2))?/,
      },
    };
  </script>

  <script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/search.min.js"></script>
  <script src="//polyfill.io/v3/polyfill.min.js?features=String.prototype.normalize"></script>
```

## Copy to clipboard

```html
<script src="//unpkg.com/docsify-copy-code"></script>
```

## Zoom image

```html
<script src="//unpkg.com/docsify/lib/plugins/zoom-image.min.js"></script>
```

## Highlight languages 

As default it's only compatible with CSS, JS and HTML. To set adittionals:

```html
<script src="//unpkg.com/prismjs/components/prism-bash.min.js"></script>
<script src="//unpkg.com/prismjs/components/prism-php.min.js"></script>
```

## Pagination

```html
<script>
window.$docsify = {
  // ...
  pagination: {
    previousText: '上一章节',
    // or
    nextText: {
      '/en/': 'NEXT',
      '/': '下一章节'
    },
    crossChapter: true,
    crossChapterText: true,
  },
}
</script>

<script src="//unpkg.com/docsify-pagination/dist/docsify-pagination.min.js"></script>
```

## PDF Preview - Embed Plugin

```html
<!-- PDFObject.js is a required dependency of this plugin -->
<script src="//cdnjs.cloudflare.com/ajax/libs/pdfobject/2.1.1/pdfobject.min.js"></script> 
<!-- This is the source code of the pdf embed plugin -->
<script src="path-to-file/docsify-pdf-embed.js"></script>
<!-- or use this if you are not hosting the file yourself -->
<script src="//unpkg.com/docsify-pdf-embed-plugin/src/docsify-pdf-embed.js"></script>
```

```md
### Here are some of your previous markdown contents
blah blah blah

```pdf
	path-to-the-pdf-file
\```
```

## Navbar

```html
<!-- index.html -->

<body>
  <nav>
    <a href="#/">EN</a>
    <a href="#/zh-cn/">简体中文</a>
  </nav>
  <div id="app"></div>
</body>



<!-- index.html -->

<script>
  window.$docsify = {
    loadNavbar: true
  }
</script>
```

```md
<!-- _navbar.md -->

* Getting started

  * [Quick start](quickstart.md)
  * [Writing more pages](more-pages.md)
  * [Custom navbar](custom-navbar.md)
  * [Cover page](cover.md)

* Configuration
  * [Configuration](configuration.md)
  * [Themes](themes.md)
  * [Using plugins](plugins.md)
  * [Markdown configuration](markdown.md)
  * [Language highlight](language-highlight.md)
```