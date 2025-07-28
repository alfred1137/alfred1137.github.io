---
description: Outlines the technologies used, development setup, technical constraints, and dependencies for the Leyton Orient CM 202503 project wiki.
author: Alfred
version: 1.0
tags: ["tech-context", "technologies", "development-setup", "constraints", "dependencies"]
---
# Tech Context: Leyton Orient EA FC 25 Wiki

## Technologies Used
*   **Markdown:** The primary language for writing all wiki content.
*   **Git:** Used for version control of the entire wiki repository.
*   **GitHub Wiki:** The hosting platform for the wiki, providing web-based access and integration with Git.
*   **Mermaid.js:** Used for generating diagrams (e.g., flowcharts, sequence diagrams) within Markdown files to visualize system architecture or processes.
*   **Image Formats:** Primarily PNG for screenshots and custom graphics. PDF for documents like transfer summaries and statistics.
*   **HTML `details`/`summary` tags:** Used within Markdown for creating collapsible sections.

## Development Setup
*   **Local Text Editor:** Any Markdown-compatible text editor (e.g., VS Code) can be used for content creation and editing.
*   **Git Client:** A Git client (e.g., Git Bash, VS Code's integrated Git) is required for cloning the repository, committing changes, and pushing updates to GitHub.
*   **Image Editing Software:** Tools like Photoshop, GIMP, or Paint.NET are used for preparing screenshots and creating custom graphics.
*   **PDF Viewer/Editor:** For reviewing and potentially generating PDF reports from the game.

## Technical Constraints
*   **GitHub Wiki Limitations:** While versatile, GitHub Wiki has certain limitations compared to dedicated website builders (e.g., limited custom styling beyond basic Markdown, reliance on specific HTML tags for advanced features like collapsible sections).
*   **Static Content:** The wiki is purely static content; there is no backend database or dynamic scripting involved. All interactivity is client-side (e.g., collapsible sections).
*   **Image Hosting:** Images must be hosted publicly (e.g., within the GitHub repository itself) and referenced via absolute URLs for consistent display.
*   **Markdown Flavor:** Adherence to GitHub Flavored Markdown (GFM) is important for consistent rendering.

## Dependencies
*   **EA FC 25 Game:** The source of all content and data for the wiki.
*   **GitHub Account:** Required for hosting the wiki and managing the repository.
*   **Internet Connection:** Necessary for accessing GitHub Wiki and pushing/pulling repository changes.
*   **Local Machine:** A computer with sufficient resources to run the game, text editor, and Git client.

## Tool Usage Patterns
*   **`write_to_file` / `replace_in_file`:** Used by the AI (Cline) to create new Markdown files or modify existing ones, ensuring adherence to content and formatting guidelines.
*   **`execute_command`:** Used for system operations like creating directories (`mkdir`) or potentially running local scripts for content generation (though not currently in use for this project).
*   **`read_file`:** Used by the AI to understand existing content and context before making modifications.
*   **`list_files`:** Used by the AI to explore the project structure and identify relevant files.
