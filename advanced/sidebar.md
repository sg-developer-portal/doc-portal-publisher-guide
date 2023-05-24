# Sidebar Plugin

The Sidebar plugin allows you to nest your page links into interactive folders
you can collapse and uncollapse!

## Setup

### Step 1: Configure docsify-sidebar-collapse plugin

Add the following code to the HTML file where you initialize Docsify:

```html
	window.$docsify = {
		enableSidebarCollapse: true
	};
```

This configuration enables the plugin to toggle on or off.

### Step 2: Insert style/script into 

Insert the necessary styles and scripts into your Docsify document. Ensure the 
following code is inside the `head` section of you HTML file:

```html
<head>
    <link rel="stylesheet" href="//cdn.jsdelivr.net/npm/@sg-developer-portal/doc-theme-default@0.0.13/public/dist/doc.css">
</head>
```

This code imports the required CSS stylesheets for the theme of the Docisfy page.

Add the following code to the <body> section of your HTML file:

```html
<body>
    <script src="//cdn.jsdelivr.net/npm/@lx0f/docsify-sidebar-collapse@latest/dist/docsify-sidebar-collapse.bundle.js"></script>
</body>
```

This code imports the JavaScript file for the docsify-sidebar-collapse plugin.

### Step 3: Create/Update your sidebar markdown file

To create a top level category/section:

```md
Category/Section

- Links
...
```

To create a folder:

```md
- Folder
    - [Link](link/to/file)
```

To create a link folder:

```md
- [Link Folder](link/to/file)
    - [Nested Link](link/to/another/file)
```

## Example

### Markdown

```md
Installation and Setup

- Installation Guide
    - [Windows Installation](install-guide/windows.md)
    - [Mac Installation](install-guide/mac.md)
    - [Linux Installation](install-guide/linux.md)
- [User Guide](user-guide/overview.md)
    - [Getting Started](user-guide/getting-started.md)
    - [Configuration](user-guide/configuration.md)
- API Reference
    - [API Documentation](api-reference/api-documentation.md)

Usage and Support

- Troubleshooting
    - Common Issues
        - [Error Messages](troubleshooting/error-messages.md)
        - [Troubleshooting FAQ](troubleshooting/faq.md)
    - [Known Issues](troubleshooting/known-issues.md)
- Support
    - [Contact Us](support/contact-us.md)
    - [Community Forums](support/community-forums.md)
- [Release Notes](release-notes/overview)
    - [Version 1.0](release-notes/v1.0.md)
    - [Version 2.0](release-notes/v2.0.md)
```

### Output

![Example Sidebar Output](../assets/example-sidebar.gif)

