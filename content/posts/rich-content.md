+++
title = "Rich Content"
description = "A brief description of Hugo Shortcodes"
date = 2020-08-26
+++

d3c3nt ships with several custom shortcodes to augment CommonMark and add additional functionality to your posts, in addition to those [already provided by Zola][built-in].
`video`, `image`, `gif`, `audio`, and `emoji` were created as simple, privacy-friendly tools for you to use in your markdown.<!-- more -->

## Video

The `video` shortcode takes an array of strings called `sources` and returns a `<video>` tag. Each string in the `sources` array should be a path to a video file of a different
type (`webm`, `mp4`, etc). Each individual source is then converted into a `<source>` tag, and the element is returned.

### Usage
```rs
{{/* video(sources=["example.webm", "example.mp4"]) */}}
```
### Output
```html
{{ video(sources=["example.webm", "example.mp4"]) }}
```

## Image

The `image` shortcode returns a `<picture>` tag and takes an array of strings called `sources`, and two strings called `fallback_path` and `fallback_alt`. Each string in the
`sources` array should be a path to an image file of a different type (`webp`, `png`, `jpg`, etc), which is then converted into a `<source>` tag. `fallback_path` and
`fallback_alt` are used to create an `<img>` tag for the browser to fall back on if the other formats aren't yet supported.

### Usage
```rs
{{/* image(sources=["example.webp", "example.jpg", "example.png"], fallback_path="example.png", fallback_alt="Lorem Ipsum") */}}
```
### Output
```html
{{ image(sources=["example.webp", "example.jpg", "example.png"], fallback_path="example.png", fallback_alt="Lorem Ipsum") }}
```

## GIF

The `gif` shortcode is exactly the same as the [video shortcode][video] – it takes an array of strings called `sources` and returns a `<video>` tag. The only difference is in
the exterior tag, which has four additional properties: `autoplay`, `loop`, `muted`, `playsinline`. Using the `<video>` tag in place of gifs allows for reduced file sizes, which
is important to optimize UX, especially in regions where internet is slower or less reliable.

### Usage
```rs
{{/* gif(sources=["example.webm", "example.mp4"]) */}}
```
### Output
```html
{{ gif(sources=["example.webm", "example.mp4"]) }}
```

## Audio

The `audio` shortcode – similarly to the [video shortcode][video] – takes an array of strings called `sources` and returns an `<audio>` tag. Each string in the `sources` array
should be a path to an audio file of a different type (`wav`, `ogg`, `mp3`, etc). Each individual source is then converted into a `<source>` tag, and the element is returned.

### Usage
```rs
{{/* audio(sources=["example.wav", "example.ogg", "example.mp3"]) */}}
```
### Output
```html
{{ audio(sources=["example.wav", "example.ogg", "example.mp3"]) }}
```

## Emoji

To learn how to use the `emoji` shortcode, check out the post on [emoji support in d3c3nt][emoji]!

[built-in]: https://www.getzola.org/documentation/content/shortcodes/#built-in-shortcodes
[video]: @/posts/rich-content.md#video
[emoji]: @/posts/emoji-support.md

