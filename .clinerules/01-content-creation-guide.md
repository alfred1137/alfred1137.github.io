---
description: Provides detailed instructions for writing, structuring, and styling content for the Jekyll Chirpy theme, including front matter, media handling, and special formatting.
author: Cline
version: 1.0
tags: ["content-creation", "styling", "jekyll", "chirpy-theme", "guide"]
globs: ["_posts/**/*.md", "_tabs/**/*.md", "*.md"]
---

# Content Creation and Styling Guide for Jekyll Chirpy Theme

This guide provides comprehensive instructions for writing, structuring, and styling content for the Chirpy theme, ensuring consistency and adherence to best practices.

## 1. Post Fundamentals

### 1.1 File Naming and Path
-   **Location:** All blog posts should reside in the `_posts/` directory.
-   **Format:** Files must follow the naming convention: `YYYY-MM-DD-TITLE.md` (or `.markdown`).

### 1.2 Front Matter
Front matter is essential metadata at the top of each post file, enclosed in `---`.

#### 1.2.1 Basic Structure
```yaml
---
title: TITLE # Colons are not allowed in the title.
date: YYYY-MM-DD HH:MM:SS +/-TTTT
categories: [TOP_CATEGORY, SUB_CATEGORY]
tags: [TAG]     # TAG names should always be lowercase
---
```
-   The `layout` is `post` by default and does not need to be specified.
-   The `date` requires a timezone offset (e.g., `+0800`).

#### 1.2.2 Categories and Tags
-   **Categories:** Use up to two elements to represent a hierarchy (e.g., `[Blogging, Tutorial]`).
-   **Tags:** Use zero or more elements, always in lowercase (e.g., `[writing, jekyll]`).

#### 1.2.3 Author Information
Author information is typically pulled from `_config.yml`. To override or add multiple authors:
1.  Define authors in `_data/authors.yml`:
    ```yaml
    # _data/authors.yml
    cotes:
      name: Alfred1137
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
A custom summary for the post can be provided using the `description` key. This summary will be used on the home page, in "Further Reading" sections, and for SEO.
```yaml
---
description: A short summary of the post that will appear under the title.
---
```

#### 1.2.5 Pinned Posts
To pin a post to the top of the home page, add `pin: true` to the front matter.
```yaml
---
pin: true
---
```

## 2. Post Features

### 2.1 Table of Contents (TOC)
The TOC is enabled by default. To disable it for a specific post, add `toc: false` to the front matter.
```yaml
---
toc: false
---
```

### 2.2 Comments
Comments are enabled globally in `_config.yml`. To disable them for a specific post, add `comments: false` to the front matter.
```yaml
---
comments: false
---
```

## 3. Text Elements and Typography

### 3.1 Headings
Standard Markdown headings are supported. Use specific classes for enhanced control over spacing and TOC inclusion.

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
-   `{: .mt-4 .mb-0 }`: Adds top margin and removes bottom margin.
-   `{: data-toc-skip=''}`: Prevents the heading from being included in the Table of Contents.

### 3.2 Paragraphs
Standard paragraph text is used for long-form content.

### 3.3 Lists
Various list types are supported:

**Ordered List:**
1.  First item
2.  Second item
3.  Third item

**Unordered List:**
*   Main item
    *   Sub-item
        *   Sub-sub-item

**ToDo List:**
- [ ] Task not completed
  - [x] Task completed
  - [ ] Another task

**Description List:**
```markdown
Term 1
: Definition for term 1.

Term 2
: Definition for term 2.
```

### 3.4 Block Quote
> This is a block quote. It's useful for highlighting specific text or citations.

### 3.5 Links
Standard Markdown links are supported.
`<https://example.com>`

### 3.6 Footnotes
Use `[^name]` for footnote references and define them at the end of the document.

**Example:**
```markdown
This is a sentence with a footnote[^1].

[^1]: This is the footnote content.
```

## 4. Code and Technical Text

### 4.1 Inline Code
Use backticks for `inline code` snippets.

### 4.2 Filepath
Use the `filepath` class to style filepaths for clarity.

**Example:**
```markdown
The configuration file is located at `/path/to/your/config.yml`{: .filepath}.
```

### 4.3 Code Blocks
Code blocks can be created with triple backticks. Specify the language for syntax highlighting and optionally a filename.

**Syntax Highlighting:**
```bash
if [ $? -ne 0 ]; then
  echo "The command was not successful.";
fi;
```

**With Filename:**
```sass
// _sass/jekyll-theme-chirpy.scss
@import "colors/light-typography";
{: file='_sass/jekyll-theme-chirpy.scss'}
```

### 4.4 Liquid Code Display
To display Liquid code without Jekyll processing it, use `{% raw %}` and `{% endraw %}` tags, or set `render_with_liquid: false` in the front matter (requires Jekyll 4.0+).

## 5. Media and Resources

### 5.1 URL Prefixes
To manage asset paths efficiently:
-   **Global CDN:** Set `cdn` in `_config.yml` for a site-wide media host.
-   **Post-specific path:** Set `media_subpath` in a post's front matter.
The final URL is constructed as: `[site.cdn/][page.media_subpath/]file.ext`

### 5.2 Images
#### 5.2.1 Preview Image (Social Sharing)
Provide an image with a `1200 x 630` resolution (`1.91:1` aspect ratio) for social media previews.
```yaml
---
image:
  path: /path/to/your/preview-image.png
  alt: A descriptive alt text for the image.
  lqip: data:image/webp;base64,... # Optional Low Quality Image Placeholder
---
```

#### 5.2.2 Image Placement and Styling
-   **Caption:** An italicized line directly following the image will be rendered as its caption.
-   **Size:** Always specify `width` (`w`) and `height` (`h`) to prevent layout shifts.
    ```markdown
    ![Image alt text](/path/to/image.png){: w="700" h="400" }
    ```
-   **Position:**
    -   `.normal`: Default, left-aligned.
    -   `.left` / `.right`: Float the image to the left or right.
-   **Dark/Light Mode Images:** Use separate images for light and dark modes with `.light` and `.dark` classes.
    ```markdown
    ![Light Mode Image](/path/to/light-image.png){: .light }
    ![Dark Mode Image](/path/to/dark-image.png){: .dark }
    ```
-   **Shadow Effect:** Add the `.shadow` class to images for a subtle shadow.

### 5.3 Video & Audio Embedding
Use Liquid `include` helpers for embedding media.

#### 5.3.1 External Video Platforms (YouTube, Twitch, Bilibili)
```liquid
{% raw %}{% include embed/youtube.html id='VIDEO_ID' %}{% endraw %}
{% raw %}{% include embed/twitch.html id='CHANNEL_NAME' %}{% endraw %}
{% raw %}{% include embed/bilibili.html id='VIDEO_ID' %}{% endraw %}
```

#### 5.3.2 Local or Remote Video/Audio Files
Embed media files directly.
```liquid
{% raw %}{% include embed/video.html src='/path/to/your/video.mp4' title='Video Title' autoplay=true %}{% endraw %}
{% raw %}{% include embed/audio.html src='/path/to/your/audio.mp3' title='Audio Title' %}{% endraw %}
```

## 6. Special Formatting and Rich Content

### 6.1 Prompts (Tip, Info, Warning, Danger)
Use special blockquote styles for emphasis:

**Tip:**
> This is a helpful tip to guide the user.
{: .prompt-tip }
```markdown
> This is a helpful tip to guide the user.
{: .prompt-tip }
```

**Info:**
> This is an informational message.
{: .prompt-info }
```markdown
> This is an informational message.
{: .prompt-info }
```

**Warning:**
> This is a warning message, use with caution.
{: .prompt-warning }
```markdown
> This is a warning message, use with caution.
{: .prompt-warning }
```

**Danger:**
> This is a danger message, indicating a critical issue.
{: .prompt-danger }
```markdown
> This is a danger message, indicating a critical issue.
{: .prompt-danger }
```

### 6.2 Tables
Standard Markdown tables with alignment support.

| Header 1 | Header 2 | Header 3 |
| :------- | :------: | -------: |
| Left     | Center   | Right    |
| Align    | Aligned  | Aligned  |

### 6.3 Mathematics (MathJax)
Enable MathJax by adding `math: true` to the front matter.

**Block-level equation:**
```latex
$$
\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}
$$
```

**Inline equation:**
The value of $\pi$ is approximately 3.14159.

### 6.4 Diagrams (Mermaid)
Enable Mermaid diagrams by adding `mermaid: true` to the front matter.

```mermaid
gantt
  title Project Timeline
  section Planning
  Requirement Gathering :done, m1, 2023-01-01, 7d
  Design :done, m2, after m1, 10d
  section Development
  Implementation : active, m3, after m2, 20d
  Testing : m4, after m3, 10d
  section Deployment
  Staging : m5, after m4, 5d
  Production : m6, after m5, 2d
