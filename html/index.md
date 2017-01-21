# HTML Code Style

This document outlines the way we should approach writing HTML markup. By following this document closely, we can ensure that anyone who touches a House House project can get up and writing quickly and efficiently, while also standardizing writing principles and accessibility practices. Every line of code should appear to be written by a single person, no matter the number of contributors.

This document borrows philosophies, ideas, and rules from [Google’s HTML Style Guide](https://google.github.io/styleguide/htmlcssguide.xml) and [Code Guide by @mdo](http://codeguide.co/#html).


***


### DOCTYPE

All HTML documents should begin by referencing the HTML5 doctype. (We write it all lowercase since the DOCTYPE declaration is not case sensitive.) There’s no reason why documents should be written in anything less than HTML5, therefore `<!doctype html>` should be our default.

```
<!doctype html>
```

This can be expressed in Jade/Pug as:

```
doctype
```

***


### General Formatting

Use a new line for every block, list or table element and indent every such child element.

```
<blockquote>
    <p><em>Space</em>, the final frontier.</p>
</blockquote>

<ul>
    <li>Moe</li>
    <li>Larry</li>
    <li>Curly</li>
</ul>
```

This can be expressed in Jade/Pug as:

```
blockquote
    p #[em Space], the final frontier

ul
    li Moe
    li Larry
    li Curly
```


***


### Indentation Spaces

Nested elements should be indented with four spaces, not tabs.

```
<!-- Recommended: four spaces -->
<div>
    <p>This is indented with four spaces</p>
</div>

<!-- NOT recommended: two spaces -->
<div>
  <p>This is indented with two spaces</p>
</div>

<!-- NOT recommended: tabs -->
<div>
	<p>This is indented with a tab</p>
</div>
```


***


### Close HTML Elements

Even though HTML5 can automatically close tags, we should always opt to close non-self-closing elements (e.g. `</body>`).

Self-contained elements (e.g. `<meta charset="utf-8"/>`) should always be self-closed — make sure they have a trailing slash at the end.

If you are writing Jade/Pug, you can omit these instructions since it will be automatically handled by the preprocessor.

```
<!-- No -->
<p>Lorem ipsum dolor sit amet.
<ul>
    <li>Foo
    <li>Bar
    <li>Baz
</ul>

<!-- Yes -->
<p>Lorem ipsum dolor sit amet.</p>
<ul>
    <li>Foo</li>
    <li>Bar</li>
    <li>Baz</li>
</ul>
```


***


### Attribute Values

When writing attribute values, always quote their value, even when writing HTML5. Use double quotation marks `"` rather than single quotation marks `'` unless writing Jade/Pug, in which case use single quotation marks `'`.

```
<!-- NOT Recommended -->
<input type=text>
<a href='/' class='button'></a>

<!-- Recommended -->
<input type="text">
<a href="/" class="button"></a>
```


***


### Attribute Order


> HTML attributes should be listed in an order that puts the most commonly-used attributes first:
>
> 1. Styling attributes: `class`
> 2. Name attributes: `id`, `name`
> 3. Custom attributes: `data-*`
> 4. Connection attributes: `src`, `for`, `type`, `href`, `value`
> 5. Auxiliary attributes: `title`, `alt`
> 6. Accessibility attributes: `aria`, `role`


***


### Omit `[type]` on `<link>` and `<script>`

Do not use type attributes for style sheets (unless not using CSS) and scripts (unless not using JavaScript).

Specifying type attributes in these contexts is not necessary as HTML5 implies text/css and text/javascript as defaults. This can be safely done even for older browsers.

```
<!-- NOT recommended -->
<link rel="stylesheet" href="//www.google.com/css/maia.css"
    type="text/css">

<!-- Recommended -->
<link rel="stylesheet" href="//www.google.com/css/maia.css">
```

```
<!-- No -->
<script src="//google.com/js/gweb/analytics/autotrack.js"
    type="text/javascript"></script>

<!-- Yes -->
<script src="//google.com/js/gweb/analytics/autotrack.js"></script>
```
