+++
title = "Docs"
+++

# Configuration

## Navbar

To customize the navbar, add a `d3_nav` property to your `config.toml`
in the `[extra]` section. The `d3_nav` variable should be an array of
objects, which each have `name` and `path` values. `name` will be used
as the link's text, and `path` will be used as the `href` value.

### Example
```toml
d3_nav = [
  { name = "HOME", path = "/" },
  { name = "POSTS", path = "/posts/" }
]
```
### Output
```html
<nav>
  <a href="/">HOME</a>
  <a href="/posts/">POSTS</a>
</nav>
```

## Favicon

To customize the favicon, add a `d3_icon` property to your `config.toml`
in the `[extra]` section. The `d3_icon` variable should be a string path
to an image in the static directory. At the moment the icon generation
is pretty simple, but this will change in the future to support a more
[realfavicongenerator.net]-esque approach.

### Default Config
```toml
d3_icon = "/icon.png"
```
### Output
```html
<link rel="icon" href="/icon.png">
```

## Metadata

To enhance SEO, you can set the `d3_twitter` variable in the `[extra]`
section of your `config.toml`. The `d3_twitter` variable should be your
Twitter username (including the "@" symbol), and will be used to set
meta tags used by Twitter for site previews.

### Example Config
```toml
d3_twitter = "@therealFIGBERT"
```
### Output
```html
<meta name="twitter:card" content="summary">
<meta name="twitter:creator" content="@therealFIGBERT">
```

[realfavicongenerator.net]: https://realfavicongenerator.net/
