# HTML Guideline

## Folder structure

The following folder structure is strongly recommended:

* `/images/`
* `/javascripts/`
* `/stylesheets/`
* `index.html`

The `fonts` folder must either be placed inside the `stylesheets` or `root` folder.


## Doctype

* The doctype must be declared as first line in the document.
* The HTML doctype should be used like this, but may as well be used in just lower case:

```html
<!DOCTYPE html>
``` 


## Element names (tags)

* HTML tags and HTML attributes must be written in lower case
* Attributes must be quoted.
* The `=` sign must not be enclosed with spaces when used for attributes.

*Bad:*
```html
<p class = "paragraph">Some text</p>
```

* All non-empty tags must be closed:

```html
<section id="section">
    <p>Some text</p>
</section>
```

* Empty tags may be closed but do not have to:

```html
<meta charset="utf-8">
```

* The `<html>`, `<head>` and `<body>` tags must not be omitted.


## Viewport

* The `<meta>` viewport must be set if the website should be accessible for smartphones and tablets.
* A possible and recommended viewport `<meta>` is:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```



## CSS and JavaScript

* Inline CSS must be avoided if possible.
* CSS and JavaScript must only be used in an external file, if possible.


## File

* A pure HTML file must have the `.html` extension.



## Source

* [W3Schools (conventions)](http://www.w3schools.com/html/html5_syntax.asp)