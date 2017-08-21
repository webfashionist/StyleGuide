# CSS Guideline


## Style definition

* Only up to one (0 or 1) space must be added before the opening brackets
* Only up to one (0 or 1) space must be added after the colon.
* Every declaration must end with a semicolon.
* Every CSS definition must be consistent with the others.
* Style definitions must be seperated with a line (two line breaks).


```css
.someClass {
    attribute: value;
}

.anotherClass {
    attribute: value;
}
```


## ID vs Class

* IDs must only be used once per page.
* Classes must be used if the element has (none, ) one or more occurences on a single page.


## ID and Class naming

* Meaningful names must be used.
* ID and class names must be as short as possible, but as long as necessary.

*Bad:*
```css
#navigation {}

.atr {}
```

*Good:*
```css
#nav {}

.author {}
```

* Component names must consist of different words seperated by a `-` (dash).

```css
.btn {}
.btn-blue {}
```

* Components can have different states. These states must be defined with a seperate class:

```css
.btn.is-active {}
```


## Properties

* Shorthand properties must be used, if possible.


*Bad:*
```css
.someClass {
    padding-top: 20px;
    padding-right: 20px;
    border-top-style: none;
}
```

*Good:*
```css
.someClass {
    padding: 20px 20px 0 0;
    border-top: none;
}
```

## Property values

* Single quotes (`'`) must be used rather than double quotes (`"`) for attribute selectors or property values.

*Exception: If you need to use the `@charset` rule, use the double quotes: [Single quotation marks are not allowed here](https://www.w3.org/TR/CSS21/syndata.html#charset)*

* Omit unit specification after “0” values, if not required.



## Sources

* [Google HTML/CSS Style Guide](https://google.github.io/styleguide/htmlcssguide.xml#CSS_Style_Rules)
* [CSS Naming Conventions: Fewer Rules, more Fun](https://medium.com/@drublic/css-naming-conventions-less-rules-more-fun-12af220e949b)
