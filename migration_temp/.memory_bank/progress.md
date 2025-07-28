---
description: Tracks the current status, what works, what's left to build, and the evolution of project decisions for the Leyton Orient CM 202503 project wiki.
author: Alfred
version: 1.0
tags: ["progress", "status", "roadmap", "known-issues"]
---
# Progress: Leyton Orient CM 202503 Wiki

## Current Status
The **Leyton Orient** EA FC 25 wiki is actively being developed and updated. Multiple chapters covering various in-game seasons have been created, and the core structure for documenting the managerial journey is in place. The integration of visual resources (images, PDFs) is ongoing, and efforts are being made to ensure consistent adherence to the defined style guides.

## What Works
*   **Chapter Structure:** The chronological chapter system (`Chapter-XX-*.md`) is effective for organizing the narrative flow of the game seasons.
*   **Basic Content Creation:** New Markdown files can be easily created and populated with text.
*   **Image Embedding:** Images hosted on GitHub Wiki are successfully embedded using absolute URLs.
*   **Collapsible Sections:** The HTML `details`/`summary` tags are functioning correctly for hiding/showing content.
*   **Version Control:** All content is under Git version control, allowing for tracking changes and collaboration.
*   **Style Guide Integration:** The `.clinerules` are being applied to new content, promoting consistency.

## What's Left to Build / Improve
*   **Comprehensive Player Profiles:** While some player mentions exist, dedicated, in-depth profiles for key players with their development arcs are needed.
*   **Detailed Financial Reporting:** More granular financial data and analysis (e.g., profit/loss statements, wage bill trends) could be integrated.
*   **Tactical Deep Dives:** More extensive explanations of tactical philosophies, specific instructions, and their evolution over seasons.
*   **Interactive Elements:** While static, exploring minor interactive elements (if supported by GitHub Wiki or simple Markdown extensions) could enhance engagement.
*   **Automated Content Generation/Validation:** Investigate if any aspects of content creation (e.g., generating summary tables from game data) or style validation could be automated.
*   **Community Contribution Guidelines:** If opening up to external contributions, clear guidelines for contributing content would be necessary.
*   **Searchability/Tagging:** Improve the discoverability of specific topics or players within the wiki.

## Known Issues
*   **Manual Style Adherence:** Currently, adherence to `BlogStyle.md` and `NameFormat.md` is largely manual, increasing the risk of inconsistencies.
*   **Image Path Management:** While absolute URLs work, ensuring all new images are uploaded to the correct `Resources/` subdirectories and linked correctly requires careful attention.
*   **Content Overlap:** Some information might be duplicated across chapters or between chapters and static pages (e.g., `Club-Profile.md`).

## Evolution of Project Decisions
*   **Initial Focus on Narrative:** The project began with a strong emphasis on storytelling the managerial journey.
*   **Increased Emphasis on Data/Visuals:** Over time, the importance of integrating game statistics, transfer data, and visual aids became apparent to provide more comprehensive insights.
*   **Formalized Style Guides:** The introduction of `.clinerules` reflects a move towards more structured and consistent documentation practices.
*   **Shift to Absolute Image Paths:** Early attempts with relative paths led to rendering issues, prompting the switch to absolute URLs for reliability.
