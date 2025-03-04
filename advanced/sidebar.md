# Using the Sidebar Plugin

# Overview

The docsify library's sidebar is good, but it can be _better_. The
[docsify-sidebar-collapse](https://github.com/sg-developer-portal/docsify-sidebar-collapse)
project overrides the docsify library's render sidebar function at runtime
allowing it total and full control over how the sidebar can be rendered into the
DOM!

## Features

- 🪹 Nested links 🪹
- 🔥 Collapsible links 🔥
- ✨ Animations ✨
- 🚦 Link highlights 🚦

## Installation & Setup

1. Insert the sidebar CSS link into the `index.html` file~ You can insert it
   almost anywhere in the file... but the best practise is to have inserted in your
   `<head> ... </head>` tag!

```html
<!-- Example: -->

<head>
  <!-- your other stuffs... -->
  <link
    rel="stylesheet"
    href="https://cdn.jsdelivr.net/npm/@developerportalsg/docsify-sidebar-collapse@2.0.7/dist/index.css"
  />
</head>
```

2. Insert the sidebar JS link into the `index.html` file~ You can insert it
   almost anywhere in the file... but the best practise is to have inserted at the
   end of your `<body> ... </body>` tag!

```html
<!-- Example: -->

<body>
  <!-- your other stuffs... -->
  <script
    defer
    src="https://cdn.jsdelivr.net/npm/@developerportalsg/docsify-sidebar-collapse@2.0.7/dist/index.js"
    integrity="sha256-IQ+Vb8nvh6Em+4DUZswgICb3wl2N6wWlKIJlfj57vjY="
    crossorigin="anonymous"
  ></script>
</body>
```

3. Configure the properties `enableSidebarCollapse` and `nameLink` in your docisfy
   configuration!

- `enableSidebarCollapse` is a boolean flag that determines if the render sidebar
  will be overrided.
- `nameLink` is a string that determines your documents "base path".

> Configuring your `nameLink` is important as it determines the "root" of your
> documentation page! For example, if `nameLink` is set to `/docs/my-awesome-doc`,
> sidebar links that point to `/`, (e.g. `[link](/)]`) will now point to `/docs/my-awesome-doc`.

```html
<!-- Example: -->
<script>
  window.$docsify = {
    enableSidebarCollapse: true,
    nameLink: "/docs/your-awesome-slug",
  };
</script>
```

## Usage

### Example

```md
Section One

- [Overview](overview)
- [Advanced](advanced)
  - [Feature One](advanced/feature-one)
  - [Feature Two](advanced/feature-two)
    - [Secret Feature...](advanced/secret)

Section Two

- [Nested](nested)
```

> Note! If your documentation has nested sidebars, make sure to include a link
> that helps your users to go back to the previous section / one level back.
>
> ```md
> <!-- Example: -->
>
> - [Content Here](./content)
> - [Content There](./content-there)
>
> ---
>
> - [Back](../overview)
> ```
>
> `---` creates a horizontal line, this helps create a visual seperation between
> your content links and navigation links.

### Rules

We tried our best to keep the plugin compatible with existing `_sidebar.md`s,
but in case it breaks, here are two rules to help streamline your sidebar
making shenanigans!

1. One Line, One Link

```md
<!-- Correct ✅ -->

- [Link](link)
- [Another Link](another-link)
  - [Nested One](nested/one)
  - [Nested Two](nested/two)

<!-- Wrong ❌ -->

- [Inside](inside) and [Outside](outside)
- [Seperated](seperated) and [Superstitious](https://superstitious.com)
```

2. Keep Everything Inside The Link

```md
<!-- Correct ✅ -->

- [Link](link)
- [Another Link](another-link)
  - [Nested One](nested/one)
  - [Nested Two](nested/two)

<!-- Wrong ❌ -->

- [Inside](inside) and Outside
- [Seperated](seperated) and Superstitious
```

3. Decorate Inside Links Fully

```md
<!-- Correct ✅ -->

- [_Italicised_](italicised)
- [**Bolded**](bolded)
- [_Whole Style I_](whole-style/i)
- [**Whole Style B**](whole-style/b)

<!-- Wrong ❌ -->

- _[Italicised](italicised)_
- **[Bolded](bolded)**
- [Partially _Italicised_](partial/italicised)
- [Partially **Bolded**](partial/bolded)
```

<!--
Dear Firefox users,

This update is my aplogy to you for neglecting compatibility with firefox for the
previous sidebar update. I hope this update makes up for it and that it helps
your readers have a better experience using your documentation 🙏.

Sincerely,
Loofes Doofes
-->
