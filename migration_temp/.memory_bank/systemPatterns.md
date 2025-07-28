---
description: Describes the system architecture, key technical decisions, and design patterns used in the Leyton Orient CM 202503 project wiki.
author: Alfred
version: 1.0
tags: ["system-patterns", "architecture", "design-patterns", "technical-decisions"]
---
# System Patterns: Leyton Orient CM 202503 Wiki

## System Architecture
The **Leyton Orient** EA FC 25 wiki is structured as a static content repository, primarily using Markdown files. It leverages GitHub Wiki as its hosting platform, which provides version control and a web-based interface for viewing the content.

```mermaid
graph TD
    A[Markdown Files] --> B[GitHub Repository]
    B --> C[GitHub Wiki]
    C --> D[Web Browser (User)]
    E[Image Resources] --> B
    F[PDF Resources] --> B
    G[Local Development Environment] --> A
    G --> E
    G --> F
```

## Key Technical Decisions
*   **Markdown for Content:** Chosen for its simplicity, readability, and ease of version control. It allows for quick content creation and editing without complex tooling.
*   **GitHub Wiki as Platform:** Provides free hosting, integrated version control (Git), and a familiar interface for collaborative documentation. It also supports direct image embedding.
*   **Centralised Resource Management:** All images and PDF documents are stored in a dedicated `Resources/` directory within the repository, making them easily accessible and manageable.
*   **Absolute Image Paths:** Using absolute URLs for images hosted on GitHub Wiki (`https://github.com/alfred1137/LOFC-CM-202503/wiki/Resources/`) ensures that images render correctly regardless of where the Markdown file is viewed (e.g., directly on GitHub, in a local Markdown viewer, or if the wiki is cloned). This avoids issues with relative paths in different contexts.
*   **Collapsible Sections (HTML `details`/`summary`):** Implemented to manage content density and improve readability for longer sections or supplementary information, allowing readers to expand details only if interested.

## Design Patterns in Use
*   **Content-as-Code:** The entire wiki content is treated as code, managed under version control (Git), allowing for tracking changes, collaboration, and rollbacks.
*   **Modular Documentation:** Content is broken down into logical chapters and sections (separate Markdown files), promoting reusability and easier maintenance.
*   **Centralised Configuration/Styling:** The `.clinerules` directory acts as a centralized place for defining content style, tone, and formatting, ensuring consistency across all wiki pages.

## Component Relationships
*   **Chapters (`Chapter-XX-*.md`):** These are the primary content units, each focusing on a specific period or event in the game. They link to each other chronologically.
*   **Resources (`Resources/`):** This directory contains all media assets (images, PDFs, PPTX) that are embedded or referenced within the Markdown chapters.
*   **Style Guides (`.clinerules/rules/*.md`):** These Markdown files define the stylistic and formatting rules that all content creators (including AI) should follow.
*   **Home (`Home.md`):** The entry point for the wiki, likely providing an overview and navigation to the chapters.
*   **Club Profile (`Club-Profile.md`):** Provides static information about **Leyton Orient**.

## Critical Implementation Paths
*   **Content Creation Workflow:** Writing new chapters involves creating a new Markdown file, populating it with narrative and data, and embedding relevant images/PDFs using the specified absolute URL format.
*   **Image Embedding:** Ensuring correct image paths is crucial for visual content to display properly on the GitHub Wiki.
*   **Style Adherence:** New content must consistently follow the `BlogStyle.md` and `NameFormat.md` rules to maintain a professional and uniform appearance.
