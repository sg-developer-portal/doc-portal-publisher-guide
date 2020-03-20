# Docsify configuration

Documentation portal uses a standard set of Docsify settings and styles to render your documentation. It does not read from your repository's `index.html` file. Some of these settings are configurable [from the portal](#manually-configurable-docsify-settings).

To see exactly how your own documentation pages would look like, use the following settings in your index.html file.

```html
<!DOCTYPE html>
<html>
  <head>
    <!-- Styles used in the Documentation Portal -->
    <link
      rel="stylesheet"
      href="https://unpkg.com/@docs-gov-sg/doc-theme-default/public/dist/doc.css"
    />
  </head>
  <body>
    <div id="app"></div>
    <script>
      window.$docsify = {
        el: "#app",
        loadSidebar: true,
        subMaxLevel: 2, // For automatic 2nd level headings
        search: "auto", // Search pages defined on your sidebar
        coverpage: true,
        themeColor: "#0c60c7"
      };
    </script>
    <script src="//unpkg.com/docsify/lib/docsify.min.js"></script>
    <script src="//unpkg.com/docsify/lib/plugins/search.min.js"></script>
  </body>
</html>
```

## Manually configurable Docsify settings

![Docsify settings](../assets/docsify_settings.png ':size=300%')

You can specify certain configurations that would be present on the`window.$docsify` object when publishing.

### name

This takes the value set for your documentation's display name

### basePath

If you want to have your markdown files or other assets reside in an inner directory of your git repo, e.g. docs/

Defaults to empty string (`''`)

### homepage

File name for your home page. 

Defaults to `README.md`

### coverpage

Enable this to render a cover page.

Defaults to `false`.

### onlyCover

Enable this to only present the cover page as your home page.

Defaults to `false`.
