# Using and Customising the Docsify Accordion Plugin

The Accordion plugin allows you to create collapsible sections of content. This is useful for long pages with sections that are not always relevant to all readers.

## Overview
The SGDS Accordion is a custom implementation of the `<summary>` and `<details>` elements in Markdown, designed to provide a consistent and visually appealing accordion experience using the Singapore Government Design System (SGDS).

This overview will guide you on how to use the SGDS Accordion to replace the standard `<summary>` and `<details>` in Markdown.

### Step 1: Configure docsify-accordion-plugin
To get started, you need to configure the docsify-accordion-plugin in your Docsify project. Add the following code to the HTML file where you initialize Docsify:

```html
<script>
	window.$docsify = {
		useSGDSAccordion: true
	};
</script>
```

This configuration enables the use of the SGDS (Singapore Government Design System) accordion style for your accordions.

### Step 2: Insert style/script into docsify document
Next, you need to insert the necessary styles and scripts into your Docsify document. Add the following code to the `<head>` section of your HTML file:

```html
<head>
	<!-- Insert your different plugins here... -->
	<link rel="stylesheet" href="https://unpkg.com/@developerportalsg/docsify-accordion-plugin@latest/dist/accordion.css" />
	<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@govtechsg/sgds@1.4.0/css/sgds.css" />
</head>
```

This code imports the required CSS stylesheets for the accordion plugin and the SGDS styles for a consistent design.

Then, add the following code to the <body> section of your HTML file:

```html
<body>
	<!-- Insert your different plugins scripts here... -->
	<script src="https://unpkg.com/@developerportalsg/docsify-accordion-plugin@latest/dist/docsify-plugin-accordion.min.js"></script>
</body>
```

This code imports the JavaScript file for the docsify-accordion-plugin.

### Step 3: Create accordions using markdown
You can now create accordions using markdown syntax. Here's an example:

```html
<details>
<summary>This is a super cool title</summary><!-- Good place for a CTA (Call to Action) -->
  <!-- leave an empty line *️⃣  -->
  <p>This is a super cool paragraph</p>
  <small>This is a super cool small paragraph</small>
  <b>Veni Vidi Vici</b>
</details>
<!-- leave an empty line *️⃣  -->
```

This code creates an accordion with the title "This is a super cool title" and the content "This is a super cool paragraph", "This is a super cool small paragraph" and "Veni Vidi Vici".

### Step 4: Customize accordions

You can also customize the accordions using various attributes. Here are some options:

| Attribute | Type | Default | Description |
| --------- | ---- | ------- | ----------- |
| `data-is-open="*VALUE*"` | `boolean` | `false` | Replace `*VALUE*` with `true` or `false` to expand the accordion on page load. |
| `data-is-size="*VALUE*"` | `string` | `medium` | Replace `*VALUE*` with `is-small`, `is-medium`, or `is-large` for various text sizes. |
| `data-is-color="*VALUE*"` | `string` | `null` | Replace `*VALUE*` with contextual text color classes (`is-danger`, `is-warning`, `is-success`, etc.) for various background colors. For more colour choices, reference <a href="https://v1.designsystem.tech.gov.sg/docs/colours/">here</a>! |

Here's an example using the attributes:

```html
<details data-is-open="true" data-is-size="small" data-is-color="is-warning">
<summary>...</summary>
...
</details>
```

In this example, the accordion will be expanded by default (data-is-open="true"), have small text size (data-is-size="small"), and a warning background color (`data-is-color

## Examples
# Accordion Test

## Raw Text

### No Header, No Body

<details data-is-open=true data-is-color="dark">
    <summary style="font-size:20px"></summary>

</details>

### Yes Header, No Body

<details>
    <summary>Heading</summary>

</details>

### No Header, Got Body

<details data-is-color='warning' data-is-size="rabak">
    <summary></summary>

<small>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Amet risus nullam eget felis. Eros in cursus turpis massa tincidunt dui ut. Eget nulla facilisi etiam dignissim diam quis. Magna etiam tempor orci eu lobortis elementum nibh tellus molestie. Varius duis at consectetur lorem donec massa. Bibendum neque egestas congue quisque. Egestas egestas fringilla phasellus faucibus. Quis viverra nibh cras pulvinar mattis nunc. A lacus vestibulum sed arcu non. Feugiat sed lectus vestibulum mattis. Quis viverra nibh cras pulvinar. Eget sit amet tellus cras adipiscing enim eu turpis egestas. Purus non enim praesent elementum. Porta lorem mollis aliquam ut porttitor leo a. Convallis aenean et tortor at. Aenean et tortor at risus viverra adipiscing at in.
</small>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Amet risus nullam eget felis. Eros in cursus turpis massa tincidunt dui ut. Eget nulla facilisi etiam dignissim diam quis. Magna etiam tempor orci eu lobortis elementum nibh tellus molestie. Varius duis at consectetur lorem donec massa. Bibendum neque egestas congue quisque. Egestas egestas fringilla phasellus faucibus. Quis viverra nibh cras pulvinar mattis nunc. A lacus vestibulum sed arcu non. Feugiat sed lectus vestibulum mattis. Quis viverra nibh cras pulvinar. Eget sit amet tellus cras adipiscing enim eu turpis egestas. Purus non enim praesent elementum. Porta lorem mollis aliquam ut porttitor leo a. Convallis aenean et tortor at. Aenean et tortor at risus viverra adipiscing at in.
</p>
</details>

### Got Header and Body
<details data-is-open=true data-is-color='primary' data-is-size="medium">
    <summary>Got header and body</summary>

<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Amet risus nullam eget felis. Eros in cursus turpis massa tincidunt dui ut. Eget nulla facilisi etiam dignissim diam quis. Magna etiam tempor orci eu lobortis elementum nibh tellus molestie. Varius duis at consectetur lorem donec massa. Bibendum neque egestas congue quisque. Egestas egestas fringilla phasellus faucibus. Quis viverra nibh cras pulvinar mattis nunc. A lacus vestibulum sed arcu non. Feugiat sed lectus vestibulum mattis. Quis viverra nibh cras pulvinar. Eget sit amet tellus cras adipiscing enim eu turpis egestas. Purus non enim praesent elementum. Porta lorem mollis aliquam ut porttitor leo a. Convallis aenean et tortor at. Aenean et tortor at risus viverra adipiscing at in.
</p>
</details>

### Got Header, Got Body And Emojis 😺

<details data-is-color="rainbow">
    <summary><h1>Heading 😺😺😺😺😺</h1></summary>
    <!-- LEAVE A GAP BELOW -->

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Amet risus nullam eget felis. Eros in cursus turpis massa tincidunt dui ut. Eget nulla facilisi etiam dignissim diam quis. Magna etiam tempor orci eu lobortis elementum nibh tellus molestie. Varius duis at consectetur lorem donec massa. Bibendum neque egestas congue quisque. Egestas egestas fringilla phasellus faucibus. Quis viverra nibh cras pulvinar mattis nunc. A lacus vestibulum sed arcu non. Feugiat sed lectus vestibulum mattis. Quis viverra nibh cras pulvinar. Eget sit amet tellus cras adipiscing enim eu turpis egestas. Purus non enim praesent elementum. Porta lorem mollis aliquam ut porttitor leo a. Convallis aenean et tortor at. Aenean et tortor at risus viverra adipiscing at in.

</details>

## Raw Text With Styles

<details>
    <summary><h3 style="color:blue;"><b><i>Big Fancy Body</i></b></h3></summary>

<small>Hello world</small>
<h1>Bye World</h1>

</details>

<details>
    <summary><h1 style="color:red;"><b><i>Big Fancy Title With Image</i></b></h1></summary>

Github Repo
![GitHub organization repository access management screenshot](../assets/github_org_repo_access.png)

</details>

## Integration with existing Docsify plugin

<details>
    <summary><h1 style="color:red;"><b><i>Very Fancy TItle</i></b></h1></summary>

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

### Nested Details/summary for dropdown content


<details>
<summary>Click me to expand!</summary>

I can contain markdown content too. Just leave a newline between markdown and HTML elements.

- Abc
- Def

</details>


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

</details>

<details>
    <summary>"><script>alert(document.cookie)</script></summary>

"><script>alert(document.cookie)</script>

Github Repo
![GitHub organization repository access management screenshot](../assets/github_org_repo_access.png)

</details>
