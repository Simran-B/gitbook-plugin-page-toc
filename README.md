# gitbook-plugin-page-toc

Add Table of Contents (ToC) to every page in your GitBook.

It adds anchors link to headings inside the page as well.

![Screenshot](https://raw.githubusercontent.com/aleung/gitbook-plugin-page-toc/master/doc/screenshot-1.png)

## Install

Add the plugin to your `book.json`:

``` json
    {
      "plugins": [ "page-toc" ],
      "pluginsConfig": {
      }
    }
```

## Configuration

- `selector` : CSS selector to select the elements to put anchors on
  - Default: `.markdown-section h1, .markdown-section h2, .markdown-section h3, .markdown-section h4`,
    which include headings from level 1 to level 4.
- `position` : Position of TOC
  - Allowed values:
    - `before-first` _(default)_ : Before the first heading
    - `top` : On top of the page

## Per-page settings

It's possible to overwrite the configuration on a per-page basis using
[Gitbook Front Matter](https://toolchain.gitbook.com/pages.html#front-matter).

Add a YAML section to the top of a page to use this:

```md
---
page-toc:
  selector: .markdown-section h2
  position: top
---
# Headline 1

Normal Markdown content here.

## Headline 1.1

Foo

## Headline 1.2

Bar

### Headline 1.2.1

Baz
```

There is also a setting to render no ToC at all for a given page:

```md
---
page-toc:
  disable: true
---
# Headline 1

Normal Markdown content here.

# Headline 1.1
```

## CSS Customization

The ToC elements have class attribute `.page-toc`. You can override the styles in `styles/website.css`.
