+++
title = "Docs"
+++

# Configuration

## Navbar

To customize the navbar, add a `nav` property to your `config.toml` in the `[extra]` section. The `nav` variable should be an array of objects, which each have `name` and `path`
values. `name` will be used as the link's text, and `path` will be used as the `href`.

### Default Config
```toml
nav = [
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

To customize the favicon, add an `icon` property to your `config.toml` in the `[extra]` section. The `icon` variable should be a string path to an image in the static directory.
At the moment the icon generation is pretty simple, but this will change in the future to support a more [realfavicongenerator.net][favicon-generator]-esque approach.

### Default Config
```toml
icon = "/icon.png"
```
### Output
```html
<link rel="icon" href="/icon.png">
```

## 404 Page

Customizing the 404 page is done with two variables: `404_image` and `404_message`, which customize the image and text respectively. `404_image` should be a string path to an
image in the static directory. `404_message` should be a string of the text you want displayed beneath the image (not including the error number, which is always there).

### Default Config
```toml
404_image = "/404.svg"
404_message = "Page Not Found"
```
### Output
```html
<div class="error">
  <img src="/404.svg" alt="404 Page Not Found">
  <strong>404</strong>
  <p>Page Not Found</p>
</div>
```

## GoatCounter

d3c3nt ships with built in [GoatCounter][gc] support. To add analytics to your site, just set the `goatcounter` variable to your site's subdomain (i.e. if your analytics are
hosted at example.goatcounter.com, you would set `goatcounter` to `"example"`) in the `[extra]` section of your `config.toml` file. d3c3nt does not include any JavaScript by
default: setting this variable will load a small amount of JS from GoatCounter's servers.

### Example Config
```toml
goatcounter = "example"
```
### Output
```html
<script data-goatcounter="https://example.goatcounter.com/count" async src="https://gc.zgo.at/count.js"></script>
```

## Metadata

To enhance SEO, you can set the `twitter` and `author` variables in the `[extra]` section of your `config.toml`. The `twitter` variable should be a string of your Twitter
username (including the "@" symbol), and will be used to set meta tags used by twitter for site previews. The `author` variable should be your name or pseudonym, and will be
used to set article metadata for web crawlers.

### Example Config
```toml
twitter = "@therealFIGBERT"
author = "FIGBERT"
```
### Output
```html
<!-- twitter -->
<meta name="twitter:creator" content="@therealFIGBERT">
<meta name="twitter:site" content="@therealFIGBERT">
<!-- author -->
<script type="application/ld+json">
  /* A bunch of stuff */
  "author": {
    "@type": "Person",
    "name": "FIGBERT"
  },
  /* Some more stuff */
</script>
```

[favicon-generator]: https://realfavicongenerator.net/
[gc]: https://www.goatcounter.com/

