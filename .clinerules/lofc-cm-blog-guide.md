---
description: Guides the generation of blog content for the LOFC-CM project, ensuring consistent tone, style, image handling, and name formatting.
author: Cline
version: 1.2
globs: ["_posts/**/*LOFC-CM*.md"]
---

# LOFC-CM Blog Content Style Guide

This guide provides specific instructions for writing content for the **Leyton Orient Career Mode (LOFC-CM)** project. It is intended to be used in conjunction with the general `01-content-creation-guide.md` for overall Jekyll Chirpy theme content guidelines. This document focuses on LOFC-CM specific requirements to avoid overlap.

## Language
*   Write in British English.

## Tone

*   **Enthusiastic and Engaging:** Maintain an enthusiastic and engaging tone to captivate readers.
    *   Example: "The journey is just beginning! The focus now is on maintaining our momentum, developing our young talent, and continuing to strengthen the squad in the January transfer window. The dream is promotion, and we're determined to make it a reality."
*   **Informative and Insightful:** Provide valuable information and insightful analysis.
    *   Example: "You'll notice that I extensively exploited the free transfer market to strengthen the squad. Many of these free agents are national team players who previously played in leagues not currently represented in the game. However, this approach comes with two significant downsides."
*   **Personal and Approachable:** Use a personal and approachable voice to connect with the audience, explicitly using first-person pronouns (I/me/my) when narrating the manager's actions, decisions, and reflections.
    *   Example: "Arriving in June 2024, I knew immediate action was needed. The squad required a significant overhaul to implement my tactical vision – a dynamic, attacking style built on a solid defensive foundation."

## Front Matter (Metadata)
All LOFC-CM blog posts must include the following front matter structure, adhering to the general rules in `01-content-creation-guide.md` for `layout` and `date` formatting:

```yaml
---
title: LOFC-CM-CH<chapter_number> | <Chapter_Title> # Colons are strictly forbidden in the title. Use hyphens or pipes as separators.
date: YYYY-MM-DD HH:MM:SS +/-TTTT
categories: ["Gaming", "EA FC 2025", "LOFC-CM-2025"]
tags: ["Leyton Orient", "Career Mode", "LOFC-CM-2025"]
description: A concise summary of the blog content. # Colons are strictly forbidden in the description.
---
```
*   **Do not include `image` in the metadata.** The `image` key for social sharing previews is handled by the general content guide.

## Image Handling
*   **Image Paths:** All image attachments MUST use paths relative to the `assets/img/` directory.
    *   **Do NOT** use local system paths like `D:\Git\LOFC-CM-2025\Docs\CH05\01.png`.

## Name Formatting

This section provides instructions on how to format names consistently in LOFC-CM blog articles.

### Club Names

-   Use **Bold** to highlight club names, e.g. `**Leyton Orient**`, `**AC Milan**`, `**Tottenham Hotspur**`
-   Use `Leyton Orient` and `the O's` interchangeably to refer to the club.

### Manager Names

-   Refer to the manager as *Filippo Inzaghi* or *Inzaghi*.
-   When referring to the AI's role as the manager, use `I/me/my` interchangeably with `*Inzaghi*`.

### Individual Names

-   Use italics for individual names, e.g., `*Dele Alli*`.

## Best Practices

*   **Use Active Voice:** Use active voice to make the writing more direct and engaging.
*   **Keep Paragraphs Short:** Keep paragraphs short and focused on a single idea.
*   **Proofread Carefully:** Proofread all content carefully for errors in grammar, spelling, and punctuation.

## Navigation

*   **Return to Chapter 00:** For all blog posts (except `LOFC-CM-CH00`), include a link at the very bottom to help readers go back to the main introduction. This link should be centered.
    ```markdown
    [Return to Chapter 00: Leyton Orient Manager Career in EA FC 2025 (Mar 2025)](/LOFC-CM-CH00/)
    {: .align-center }
    ```
    *(Note: The `.align-center` class is a common convention for centering in Jekyll themes. If it doesn't work, further investigation into the theme's CSS will be needed.)*
