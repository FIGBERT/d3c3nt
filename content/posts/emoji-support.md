+++
title = "Emoji Support"
description = "Guide to emoji usage in d3c3nt"
date = 2020-08-25
+++

Emoji can be used with the d3c3nt theme using the `emoji` shortcode in your markdown files. d3c3nt's emojis are provided by [OpenMoji][openmoji] for a consistent,
stylized look across all platforms and embedded as inline `svg`s to reduce network requests.<!-- more -->

## Shortcode

The emoji shortcode expects two parameters, `id` and `alt`.

The `id` parameter is the Unicode codepoint/s of the emoji. You can find this either from the Unicode parameter of an
emoji as listed on [the OpenMoji library][lib], or from the "Codepoints" section on [Emojipedia][emojipedia] (the section after "U+". For multiple codepoints, combine them
with a dash).

The `alt` parameter provides a description of the image for better accessibility.

## Examples
### Unicode
**Grinning Face:** {{ emoji(id="1F600", alt="A grinning face") }}
```rs
{{/* emoji(id="1F600", alt="A grinning face") */}}
```
**Flag of Antarctica:** {{ emoji(id="1F1E6-1F1F6", alt="Flag of Antarctica") }}
```rs
{{/* emoji(id="1F1E6-1F1F6", alt="Flag of Antarctica") */}}
```
### Extra Unicode
**Hacker Cat:** {{ emoji(id="1F431-200D-1F4BB", alt="Hacker Cat") }}
```rs
{{/* emoji(id="1F431-200D-1F4BB", alt="Hacker Cat") */}}
```
### Extra OpenMoji
**Flag of the United Federation of Planets:** {{ emoji(id="1F3F3-FE0F-200D-1F7E6-200D-1F30C", alt="Flag of the United Federation of Planets") }}
```rs
{{/* emoji(id="1F3F3-FE0F-200D-1F7E6-200D-1F30C", alt="Flag of the United Federation of Planets") */}}
```
**Github Logo:** {{ emoji(id="E045", alt="Github Logo") }}
```rs
{{/* emoji(id="E045", alt="Github Logo") */}}
```
**Web Syndication:** {{ emoji(id="E381", alt="Web Syndication") }}
```rs
{{/* emoji(id="E381", alt="Web Syndication") */}}
```

[openmoji]: https://openmoji.org/
[lib]: https://openmoji.org/library/
[emojipedia]: https://emojipedia.org/

