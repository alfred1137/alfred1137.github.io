---
description: A comprehensive guide for creating and styling content for the Chirpy theme.
author: Cline
version: 1.0
tags: ["content-creation", "styling", "chirpy-theme", "guide"]
---
# Content Guide

This guide provides comprehensive instructions for writing, structuring, and styling content for the Chirpy theme.

## 1. Post Fundamentals
### 1.1 File Naming and Path
-   **Location:** `_posts/`
-   **Format:** `YYYY-MM-DD-TITLE.md` (or `.markdown`)

### 1.2 Front Matter
This is the essential metadata at the top of each post file.

#### 1.2.1 Basic Structure
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

#### 1.2.2 Categories and Tags
-   **Categories:** Up to two elements, representing a hierarchy.
-   **Tags:** Zero or more elements, always in lowercase.
```yaml
---
categories: [Blogging, Tutorial]
tags: [writing, jekyll]
---
```

#### 1.2.3 Author Information
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

#### 1.2.4 Post Description
A custom summary for the post can be provided. This will be used on the home page, in "Further Reading" sections, and for SEO.
```yaml
---
description: A short summary of the post that will appear under the title.
---
```

#### 1.2.5 Pinned Posts
To pin a post to the top of the home page, add `pin: true`.
```yaml
---
pin: true
---
```

## 2. Post Features
### 2.1 Table of Contents (TOC)
The TOC is enabled by default. To disable it for a specific post:
```yaml
---
toc: false
---
```

### 2.2 Comments
Comments are enabled globally in `_config.yml`. To disable them for a specific post:
```yaml
---
comments: false
---
```

## 3. Text Elements and Typography
This section outlines the styling and formatting conventions for various text elements.

### 3.1 Headings
The theme supports standard Markdown headings, which can be styled with special classes.
```markdown
# H1 — heading
{: .mt-4 .mb-0 }

## H2 — heading
{: data-toc-skip='' .mt-4 .mb-0 }

### H3 — heading
{: data-toc-skip='' .mt-4 .mb-0 }

#### H4 — heading
{: data-toc-skip='' .mt-4 }
```

### 3.2 Paragraphs
Standard paragraph text is used for long-form content.

### 3.3 Lists
Several list types are available:

**Ordered List:**
1.  Firstly
2.  Secondly
3.  Thirdly

**Unordered List:**
*   Chapter
    *   Section
        *   Paragraph

**ToDo List:**
- [ ] Job
  - [x] Step 1
  - [ ] Step 2
  - [ ] Step 3

**Description List:**
```markdown
Sun
: the star around which the earth orbits

Moon
: the natural satellite of the earth, visible by reflected light from the sun
```

### 3.4 Block Quote
> This line shows the _block quote_.

### 3.5 Links
Standard markdown links are supported: `<http://127.0.0.1:4000>`

### 3.6 Footnotes
Footnotes can be created using `[^name]` and defined later in the document.

**Example:**
```markdown
Click the hook will locate the footnote[^footnote].

[^footnote]: The footnote source
```

## 4. Code and Technical Text
### 4.1 Inline Code
Use backticks for `inline code`.

### 4.2 Filepath
Use the `filepath` class to style filepaths.

**Example:**
```markdown
Here is the `/path/to/the/file.extend`{: .filepath}.
```
**Renders as:**
Here is the `/path/to/the/file.extend`{: .filepath}.

### 4.3 Code Blocks
Code blocks can be created with triple backticks. You can specify a language for syntax highlighting and an optional filename.

**Specific Language:**
```bash
if [ $? -ne 0 ]; then
  echo "The command was not successful.";
  #do the needful / exit
fi;
```

**Specific Filename:**
```sass
// _sass/jekyll-theme-chirpy.scss
@import
  "colors/light-typography",
  "colors/dark-typography";
```
{: file='_sass/jekyll-theme-chirpy.scss'}

### 4.4 Liquid Code Display
To show Liquid code snippets without them being processed by Jekyll, either wrap them in `{% raw %}` and `{% endraw %}` tags, or set `render_with_liquid: false` in the front matter (requires Jekyll 4.0+).

## 5. Media and Resources
### 5.1 URL Prefixes
To avoid repeating paths, you can set prefixes.
-   **Global CDN:** Set `cdn` in `_config.yml` for a site-wide media host.
-   **Post-specific path:** Set `media_subpath` in a post's front matter.

The final URL is constructed as: `[site.cdn/][page.media_subpath/]file.ext`

### 5.2 Images
#### 5.2.1 Preview Image (for social sharing)
Provide an image with a `1200 x 630` resolution (`1.91:1` aspect ratio).
```yaml
---
image:
  path: /path/to/image.png
  alt: A description of the image.
  lqip: data:image/webp;base64,... # Optional Low Quality Image Placeholder
---
```

#### 5.2.2 Image Placement and Styling
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

### 5.3 Video & Audio
Use Liquid `include` helpers to embed media.

#### 5.3.1 YouTube, Twitch, Bilibili
```liquid
{% raw %}{% include embed/youtube.html id='VIDEO_ID' %}{% endraw %}
```

#### 5.3.2 Video/Audio Files
Embed local or remote video/audio files.
```liquid
{% raw %}{% include embed/video.html src='/path/to/video.mp4' title='Demo' autoplay=true %}{% endraw %}
{% raw %}{% include embed/audio.html src='/path/to/audio.mp3' title='Demo' %}{% endraw %}
```

## 6. Special Formatting and Rich Content
### 6.1 Prompts (Tip, Info, Warning, Danger)
The theme provides special blockquote-style prompts to highlight information.

**Tip:**
> An example showing the `tip` type prompt.
{: .prompt-tip }
```markdown
> An example showing the `tip` type prompt.
{: .prompt-tip }
```

**Info:**
> An example showing the `info` type prompt.
{: .prompt-info }
```markdown
> An example showing the `info` type prompt.
{: .prompt-info }
```

**Warning:**
> An example showing the `warning` type prompt.
{: .prompt-warning }
```markdown
> An example showing the `warning` type prompt.
{: .prompt-warning }
```

**Danger:**
> An example showing the `danger` type prompt.
{: .prompt-danger }
```markdown
> An example showing the `danger` type prompt.
{: .prompt-danger }
```

### 6.2 Tables
Standard Markdown tables with alignment are supported.

| Company                      | Contact          | Country |
| :--------------------------- | :--------------- | ------: |
| Alfreds Futterkiste          | Maria Anders     | Germany |
| Island Trading               | Helen Bennett    |      UK |
| Magazzini Alimentari Riuniti | Giovanni Rovelli |   Italy |

### 6.3 Mathematics (MathJax)
To enable MathJax on a page, add `math: true` to the frontmatter.

**Block-level equation:**
```latex
$$
\sum_{n=1}^\infty 1/n^2 = \frac{\pi^2}{6}
$$
```

**Inline equation:**
When $a \ne 0$, there are two solutions.

### 6.4 Diagrams (Mermaid)
To enable Mermaid on a page, add `mermaid: true` to the frontmatter.

```mermaid
gantt
  title  Adding GANTT diagram functionality to mermaid
  apple :a, 2017-07-20, 1w
  banana :crit, b, 2017-07-23, 1d
  cherry :active, c, after b a, 1d
