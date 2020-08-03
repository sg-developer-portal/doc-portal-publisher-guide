## Docsify Markdown Extensions

?> Docsify provides [some useful extensions to markdown](https://docsify.js.org/#/helpers). Some examples are shown below.

### Content highlighting

Use `?>` and `!>` before text to highlight blocks of content:

```markdown
?> This is highlighted

!> And so am I
```

?> This is highlighted

!> And so am I

### Image resizing

```
![logo](https://docsify.js.org/_media/icon.svg)
![logo](https://docsify.js.org/_media/icon.svg ':size=50x100')
![logo](https://docsify.js.org/_media/icon.svg ':size=100')
![logo](https://docsify.js.org/_media/icon.svg ':size=45%')
```

![logo](https://docsify.js.org/_media/icon.svg)
![logo](https://docsify.js.org/_media/icon.svg ":size=50x100")
![logo](https://docsify.js.org/_media/icon.svg ":size=100")
![logo](https://docsify.js.org/_media/icon.svg ":size=45%")

### Set target attribute for link

```
[link](/example ':target=_blank')
[link](/example2 ':target=_self')
```

[link](/example ":target=_blank")
[link](/example2 ":target=_self")

### Disabled Link

```
[link](/demo ':disabled')
```

[link](/demo ":disabled")

## HTML

Some useful HTML elements are available for adding default interactivity and illustrations.

### Details/summary for dropdown content

```markdown
<hr />
<details>
  <summary>Click me to expand!</summary>

I can contain markdown content too. Just leave a newline between markdown and HTML elements.

- Abc
- Def

</details>
<hr />
```

<hr />
<details>
  <summary>Click me to expand!</summary>

I can contain markdown content too. Just leave a newline between markdown and HTML elements.

- Abc
- Def

</details>
<hr />

### Progress/meter bars

```html
<progress value="70" max="100"></progress>

<meter
  min="0" max="100"
  low="33" high="66" optimum="80"
  value="50">
Current value: 50/100
</meter>
```

<progress value="70" max="100"></progress>

<meter
  min="0" max="100"
  low="33" high="66" optimum="80"
  value="50">
Current value: 50/100
</meter>

## Markdown Syntax

``````markdown
# h1 Heading

## h2 Heading

### h3 Heading

#### h4 Heading

##### h5 Heading

###### h6 Heading

``````

# h1 Heading {docsify-ignore}

## h2 Heading {docsify-ignore}

### h3 Heading

#### h4 Heading

##### h5 Heading

###### h6 Heading

## Horizontal Rules

``````markdown

---

---

---
``````

---

---

---

## Emphasis
``````markdown

**This is bold text**

**This is bold text**

_This is italic text_

_This is italic text_

~~Strikethrough~~
``````

**This is bold text**

**This is bold text**

_This is italic text_

_This is italic text_

~~Strikethrough~~


## Blockquotes
``````markdown
> Blockquotes can also be nested...
>
> > ...by using additional greater-than signs right next to each other...
> >
> > > ...or with spaces between arrows.
``````

> Blockquotes can also be nested...
>
> > ...by using additional greater-than signs right next to each other...
> >
> > > ...or with spaces between arrows.


## Lists

Unordered

``````markdown
- Create a list by starting a line with `+`, `-`, or `*`
- Sub-lists are made by indenting 2 spaces:
  - Marker character change forces new list start:
    - Ac tristique libero volutpat at
    * Facilisis in pretium nisl aliquet
    - Nulla volutpat aliquam velit
- Very easy!
``````

- Create a list by starting a line with `+`, `-`, or `*`
- Sub-lists are made by indenting 2 spaces:
  - Marker character change forces new list start:
    - Ac tristique libero volutpat at
    * Facilisis in pretium nisl aliquet
    - Nulla volutpat aliquam velit
- Very easy!

Ordered
``````markdown
1. Lorem ipsum dolor sit amet
2. Consectetur adipiscing elit
3. Integer molestie lorem at massa

It’s important to note that the actual numbers you use to mark the list have no effect on the HTML output Markdown produces.

1. You can use sequential numbers...
1. ...or...
1. keep all the numbers as `1.`

Start numbering with offset:

57. foo
1. bar
``````

1. Lorem ipsum dolor sit amet
2. Consectetur adipiscing elit
3. Integer molestie lorem at massa

It’s important to note that the actual numbers you use to mark the list have no effect on the HTML output Markdown produces.

1. You can use sequential numbers...
1. ...or...
1. keep all the numbers as `1.`

Start numbering with offset:

57. foo
1. bar

## Code

Use the back tick character (`) to display code.

### Inline code

``````markdown
The follow text is `inline code`.
``````
The follow text is `inline code`.

### Block code "fences"

``````markdown
```
No language indicated, so no syntax highlighting in Markdown Here.
But let's throw in a <b>tag</b>.
```
``````

```
No language indicated, so no syntax highlighting in Markdown Here.
But let's throw in a <b>tag</b>.
```


### Syntax highlighting

``````markdown
```javascript
var foo = function(bar) {
return bar++;
};

console.log(foo(5));
```
``````

```javascript
var foo = function(bar) {
return bar++;
};

console.log(foo(5));
```

``````markdown
```python
s = "Python syntax highlighting"
print s
```
``````

```python
s = "Python syntax highlighting"
print s
```

### Indented code

``````markdown
    // Some comments
    line 1 of code
    line 2 of code
    line 3 of code
``````
    // Some comments
    line 1 of code
    line 2 of code
    line 3 of code

## Tables

``````markdown
| Option | Description                                                               |
| ------ | ------------------------------------------------------------------------- |
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default.    |
| ext    | extension to be used for dest files.                                      |

Right aligned columns

| Option |                                                               Description |
| -----: | ------------------------------------------------------------------------: |
|   data | path to data files to supply the data that will be passed into templates. |
| engine |    engine to be used for processing templates. Handlebars is the default. |
|    ext |                                      extension to be used for dest files. |
``````

| Option | Description                                                               |
| ------ | ------------------------------------------------------------------------- |
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default.    |
| ext    | extension to be used for dest files.                                      |

Right aligned columns

| Option |                                                               Description |
| -----: | ------------------------------------------------------------------------: |
|   data | path to data files to supply the data that will be passed into templates. |
| engine |    engine to be used for processing templates. Handlebars is the default. |
|    ext |                                      extension to be used for dest files. |

## Links

``````markdown
[link text](http://dev.nodeca.com)

[link with title](http://nodeca.github.io/pica/demo/ "title text!")

Autoconverted link https://github.com/nodeca/pica (enable linkify to see)
``````

[link text](http://dev.nodeca.com)

[link with title](http://nodeca.github.io/pica/demo/ "title text!")

Autoconverted link https://github.com/nodeca/pica (enable linkify to see)

## Images

``````markdown

![Minion](https://octodex.github.com/images/minion.png ":size=250")
![Stormtroopocat](https://octodex.github.com/images/stormtroopocat.jpg ":size=250 The Stormtroopocat")

Like links, Images also have a footnote style syntax

![Alt text][id]

With a reference later in the document defining the URL location:

[id]: https://octodex.github.com/images/dojocat.jpg ":size=400 The Dojocat"
``````
![Minion](https://octodex.github.com/images/minion.png ":size=250")
![Stormtroopocat](https://octodex.github.com/images/stormtroopocat.jpg ":size=250 The Stormtroopocat")

Like links, Images also have a footnote style syntax

![Alt text][id]

With a reference later in the document defining the URL location:

[id]: https://octodex.github.com/images/dojocat.jpg ":size=400 The Dojocat"
