# Using and Customising the Docsify Accordion Plugin

The Accordion plugin allows you to create collapsible sections of content. This is useful for long pages with sections that are not always relevant to all readers.

## Overview
The SGDS Accordion is a custom implementation of the `<summary>` and `<details>` elements in Markdown, designed to provide a consistent and visually appealing accordion experience using the Singapore Government Design System (SGDS).

This overview will guide you on how to use the SGDS Accordion to replace the standard `<summary>` and `<details>` in Markdown.

### Step 1: Configure docsify-accordion-plugin (Only relevant when editing on local)
To get started, you need to configure the docsify-accordion-plugin in your Docsify project. Add the following code to the HTML file where you initialize Docsify:

```html
<script>
	window.$docsify = {
		useSGDSAccordion: true
	};
</script>
```

This configuration enables the use of the SGDS (Singapore Government Design System) accordion style for your accordions.

### Step 2: Insert style/script into docsify document (Only relevant when editing on local)
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

## Very cool accordion!
<details>
<summary>Got header and body</summary>

<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Amet risus nullam eget felis. Eros in cursus turpis massa tincidunt dui ut. Eget nulla facilisi etiam dignissim diam quis. Magna etiam tempor orci eu lobortis elementum nibh tellus molestie. Varius duis at consectetur lorem donec massa. Bibendum neque egestas congue quisque. Egestas egestas fringilla phasellus faucibus. Quis viverra nibh cras pulvinar mattis nunc. A lacus vestibulum sed arcu non. Feugiat sed lectus vestibulum mattis. Quis viverra nibh cras pulvinar. Eget sit amet tellus cras adipiscing enim eu turpis egestas. Purus non enim praesent elementum. Porta lorem mollis aliquam ut porttitor leo a. Convallis aenean et tortor at. Aenean et tortor at risus viverra adipiscing at in.
</p>
</details>

```
<details>
<summary>Very Cool and Fancy Title</summary>

<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Amet risus nullam eget felis. Eros in cursus turpis massa tincidunt dui ut. Eget nulla facilisi etiam dignissim diam quis. Magna etiam tempor orci eu lobortis elementum nibh tellus molestie. Varius duis at consectetur lorem donec massa. Bibendum neque egestas congue quisque. Egestas egestas fringilla phasellus faucibus. Quis viverra nibh cras pulvinar mattis nunc. A lacus vestibulum sed arcu non. Feugiat sed lectus vestibulum mattis. Quis viverra nibh cras pulvinar. Eget sit amet tellus cras adipiscing enim eu turpis egestas. Purus non enim praesent elementum. Porta lorem mollis aliquam ut porttitor leo a. Convallis aenean et tortor at. Aenean et tortor at risus viverra adipiscing at in.
</p>
</details>
```
 
