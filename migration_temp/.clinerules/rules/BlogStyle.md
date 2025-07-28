---
description: Guides the generation of blog content to ensure a consistent tone and style, including image attachment and collapsible section guidelines.
globs: **/*.md
alwaysApply: false
---

# Blog Post Style Guide

## Language
*   Write in British English.

## Tone

*   **Enthusiastic and Engaging:** Maintain an enthusiastic and engaging tone to captivate readers.
    *   Example: "The journey is just beginning! The focus now is on maintaining our momentum, developing our young talent, and continuing to strengthen the squad in the January transfer window. The dream is promotion, and we're determined to make it a reality."
*   **Informative and Insightful:** Provide valuable information and insightful analysis.
    *   Example: "You'll notice that I extensively exploited the free transfer market to strengthen the squad. Many of these free agents are national team players who previously played in leagues not currently represented in the game. However, this approach comes with two significant downsides."
*   **Personal and Approachable:** Use a personal and approachable voice to connect with the audience, explicitly using first-person pronouns (I/me/my) when narrating the manager's actions, decisions, and reflections.
    *   Example: "Arriving in June 2024, I knew immediate action was needed. The squad required a significant overhaul to implement my tactical vision – a dynamic, attacking style built on a solid defensive foundation."

## Style

*   **Clear and Concise:** Write in a clear and concise manner, avoiding jargon and overly complex sentences.
*   **Well-Structured:** Organize content with clear headings, subheadings, and bullet points for easy readability.
*   **Consistent Formatting:** Use consistent formatting for headings, lists, and code blocks.
*   **Visual Appeal:** Incorporate images, videos, and other visual elements to enhance engagement.

## Content

*   **Introduction:** Start with a compelling introduction that grabs the reader's attention and outlines the main topic.
*   **Body:** Develop the main topic with supporting details, examples, and analysis.
*   **Conclusion:** Summarize the main points and provide a call to action or concluding thought.
*   **Image Attachments:**
    *   Use the following format for image attachments: `https://github.com/alfred1137/LOFC-CM-202503/Wiki/Resources/SAMPLE1.png` and not the relative path of the image within the code base, i.e. `Resources\SAMPLE1.png`. E.g. `[!Form as of 13 Oct 2024](https://github.com/alfred1137/LOFC-CM-202503/Wiki/Resources/Leyton_Orient_CM-20241013_1.png)` and not `Resources\Leyton_Orient_CM-20241013_1.png`
*   **Collapsible Sections:**
    *   Use collapsible sections (details/summary) to hide less critical or lengthy information, improving readability.
    *   Example:

        ````markdown
        <details>
          <summary>Loan of Mikey Moore <sup>click to expand</sup></summary>

        Mikey Moore, a 17-year-old English winger from Tottenham Hotspur, is considered one of the brightest prospects in English football. He has won it all at the U17 and U21 level, and has since then become Spurs' youngest-ever Premier League player. This impressive trajectory made securing his loan spell a straightforward decision for both clubs. It will provide him with valuable first-team experience and much needed reinforcement for the O's.
        </details>
        ````
*   **Images:**
    *   path to images in cloud storage are rooted at `https://github.com/alfred1137/LOFC-CM-202503/wiki/Resources/`
    *   This is instead of local path `./Resources`
    *   Example:
    `.\Resources\Banner.png` is available at `https://github.com/alfred1137/LOFC-CM-202503/wiki/Resources/Banner.png`
    `D:\Git\LOFC-CM-202503.wiki\Resources\CH05\01.png` is at `https://github.com/alfred1137/LOFC-CM-202503/wiki/Resources/CH05/01.png`
    and so on

* Allowed image arrangements
    * Type 1: signle large image, e.g.
    ```
    ![Squad Overview](mdc:https://github.com/alfred1137/LOFC-CM-202503/wiki/Resources/CH08/squad-20251102.png)
    ```
    * Type 2: 2 small ones side by side, e.g.
    ```
    <div align="center">
  <img src="https://github.com/alfred1137/LOFC-CM-202503/wiki/Resources/Lankshear_MOTM_20241221.png" width="400"> <img src="https://github.com/alfred1137/LOFC-CM-202503/wiki/Resources/Keeley_SNS_20241216.png" width="400"></div>
    ```

## Best Practices

*   **Use Active Voice:** Use active voice to make the writing more direct and engaging.
*   **Keep Paragraphs Short:** Keep paragraphs short and focused on a single idea.
*   **Proofread Carefully:** Proofread all content carefully for errors in grammar, spelling, and punctuation.

## Example

Here's an example of a well-structured blog post:

```markdown
# Title of Your Blog Post

## Introduction

[Write a compelling introduction here.]

## Section 1

[Write the content for section 1 here.]

## Section 2

[Write the content for section 2 here.]

## Conclusion

[Write a concluding paragraph here.]
