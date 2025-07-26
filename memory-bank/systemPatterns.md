# System Patterns

## 1. System Architecture

The project follows a standard Jekyll static site architecture.

```mermaid
graph TD
    A[Content & Templates] -->|Jekyll Build Process| B(Static Website);
    B -->|Hosted on| C[GitHub Pages];
    C --> D[User's Browser];

    subgraph "A[Content & Templates]"
        direction LR
        A1[Markdown Files (.md)]
        A2[Liquid Templates (.html)]
        A3[Configuration (_config.yml)]
        A4[Data Files (_data/*.yml)]
        A5[Assets (CSS, JS, Images)]
    end
```

- **Content-First:** The core of the site is the content, written in Markdown.
- **Template-Driven:** The layout and structure are defined by Liquid templates.
- **Configuration-Controlled:** Site-wide behavior is controlled by `_config.yml`.
- **Static Output:** The build process generates a self-contained `_site` directory with plain HTML, CSS, and JS files, which is then served by GitHub Pages.

## 2. Key Design Patterns

- **Separation of Concerns:**
    - **Content:** Resides in `_posts`, `_tabs`, and other Markdown files.
    - **Presentation:** Managed by HTML layouts in `_layouts` and includes in `_includes`.
    - **Styling:** Handled by Sass files in `_sass` which compile to CSS.
    - **Logic/Configuration:** Centralized in `_config.yml` and `_data` files.
- **Modularity:** The Chirpy theme is designed to be modular. Features can be enabled or disabled through configuration. The use of Jekyll plugins and includes promotes reusable components.
- **Convention over Configuration:** Jekyll itself relies heavily on this principle. For example, files in the `_posts` directory are automatically processed as blog posts, and layouts in `_layouts` are automatically available to be used by pages and posts.

## 3. Critical Implementation Paths

- **Creating a New Post:** A new Markdown file is created in the `_posts` directory with a specific filename format (`YYYY-MM-DD-title.md`) and YAML front matter.
- **Customizing Appearance:** Changes are made by overriding the theme's default styles in the `assets/css/` directory or by modifying theme variables in `_sass/`.
- **Changing Site Information:** Site title, author information, social media links, etc., are all modified within the `_config.yml` file.
