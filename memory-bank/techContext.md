# Technical Context

## 1. Core Technologies

- **Jekyll:** A static site generator written in Ruby. It takes Markdown text and Liquid templates and outputs a complete, static website.
- **GitHub Pages:** Provides hosting for the static website directly from the GitHub repository.
- **Ruby & Bundler:** The project uses Ruby as its programming language. `Bundler` is used to manage Ruby gems (dependencies) as specified in the `Gemfile`.
- **Chirpy Theme:** A specific Jekyll theme that provides the design and many of the features. It uses Bootstrap for its responsive framework.

## 2. Development and Deployment Workflow

- **Development Model:** All development will happen directly within this codebase. There will be no local Jekyll server for previewing changes.
- **Deployment Model:** The site is deployed exclusively through a GitHub Actions workflow. Any commit pushed to the `main` (or `master`) branch will trigger the workflow, which builds the Jekyll site and deploys it to GitHub Pages.
- **Configuration:** The main configuration file is `_config.yml`. This file controls site-wide settings, theme options, and plugin configurations.

## 3. Project Structure

- `_config.yml`: Main Jekyll configuration.
- `_data/`: Contains data files (e.g., `contact.yml`, `share.yml`) used by the theme.
- `_posts/`: Where blog post Markdown files are stored.
- `_tabs/`: Contains the Markdown for the main navigation tabs (About, Archives, etc.).
- `assets/`: Holds static assets like CSS, JS, and images.
- `Gemfile`: Defines the Ruby gem dependencies.
- `index.html`: The main entry point of the site.
