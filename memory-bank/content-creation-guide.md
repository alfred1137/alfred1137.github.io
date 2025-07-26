# Content Creation Guide

This guide covers the process of writing and structuring a new post for the Chirpy theme.

## File Naming and Path

-   **Location:** `_posts/`
-   **Format:** `YYYY-MM-DD-TITLE.md` (or `.markdown`)

## Front Matter

This is the essential metadata at the top of each post file.

### Basic Structure

```yaml
---
title: TITLE
date: YYYY-MM-DD HH:MM:SS +/-TTTT
categories: [TOP_CATEGORY, SUB_CATEGORY]
tags: [TAG]     # TAG names should always be lowercase
---
```

-   The `layout` is `post` by default and does not need to be specified.
-   The `date` requires a timezone offset (e.g., `+0800`).

### Categories and Tags

-   **Categories:** Up to two elements, representing a hierarchy.
-   **Tags:** Zero or more elements, always in lowercase.

```yaml
---
categories: [Blogging, Tutorial]
tags: [writing, jekyll]
---
```

### Author Information

Author info is pulled from `_config.yml` by default. To override or add multiple authors:

1.  Define authors in `_data/authors.yml`:
    ```yaml
    # _data/authors.yml
    cotes:
      name: Cotes Chung
      twitter: cotes2020
      url: https://github.com/cotes2020/
    ```
2.  Reference the author ID in the post's front matter:
    ```yaml
    ---
    author: cotes # for a single author
    # or
    authors: [cotes, another_author] # for multiple authors
    ---
    ```

### Post Description

A custom summary for the post can be provided. This will be used on the home page, in "Further Reading" sections, and for SEO.

```yaml
---
description: A short summary of the post that will appear under the title.
---
```

### Pinned Posts

To pin a post to the top of the home page, add `pin: true`.

```yaml
---
pin: true
---
```

## Post Features

### Table of Contents (TOC)

The TOC is enabled by default. To disable it for a specific post:

```yaml
---
toc: false
---
```

### Comments

Comments are enabled globally in `_config.yml`. To disable them for a specific post:

```yaml
---
comments: false
---
```

## Media and Resources

### URL Prefixes

To avoid repeating paths, you can set prefixes.

-   **Global CDN:** Set `cdn` in `_config.yml` for a site-wide media host.
-   **Post-specific path:** Set `media_subpath` in a post's front matter.

The final URL is constructed as: `[site.cdn/][page.media_subpath/]file.ext`

### Images

#### Preview Image (for social sharing)

Provide an image with a `1200 x 630` resolution (`1.91:1` aspect ratio).

```yaml
---
image:
  path: /path/to/image.png
  alt: A description of the image.
  lqip: data:image/webp;base64,... # Optional Low Quality Image Placeholder
---
```

#### Image Placement and Styling

-   **Caption:** An italicized line directly after the image becomes its caption.
-   **Size:** Always specify width and height to prevent layout shift. `w` and `h` are shortcuts for `width` and `height`.
    ```markdown
    ![Image alt](/path/to/image.png){: w="700" h="400" }
    ```
-   **Position:**
    -   `.normal`: Default, left-aligned.
    -   `.left` / `.right`: Float the image.
-   **Dark/Light Mode:** Use two images with `.light` and `.dark` classes.
    ```markdown
    ![For Light](/path/to/light.png){: .light }
    ![For Dark](/path/to/dark.png){: .dark }
    ```
-   **Shadow:** Add the `.shadow` class for a shadow effect.

### Video & Audio

Use Liquid `include` helpers to embed media.

#### YouTube, Twitch, Bilibili

```liquid
{% raw %}{% include embed/youtube.html id='VIDEO_ID' %}{% endraw %}
```

#### Video/Audio Files

Embed local or remote video/audio files.

```liquid
{% raw %}{% include embed/video.html src='/path/to/video.mp4' title='Demo' autoplay=true %}{% endraw %}
{% raw %}{% include embed/audio.html src='/path/to/audio.mp3' title='Demo' %}{% endraw %}
```

## Advanced Formatting

### Liquid Code Display

To show Liquid code snippets without them being processed by Jekyll, either wrap them in `{% raw %}` and `{% endraw %}` tags, or set `render_with_liquid: false` in the front matter (requires Jekyll 4.0+).

### Mathematics (MathJax)

Enable on a per-post basis with `math: true` in the front matter.

-   **Block Math:** Use `$$...$$` on separate lines.
-   **Inline Math:** Use `$$...$$` within a line of text.
-   **Inline Math in Lists:** Escape the first dollar sign: `\$$...$$`.

### Diagrams (Mermaid)

Enable on a per-post basis with `mermaid: true` in the front matter.

```mermaid
graph TD
    A[Start] --> B{Is it working?};
    B -- Yes --> C[End];
    B -- No --> A;
