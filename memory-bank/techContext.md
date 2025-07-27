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

## 4. Upgrade and Maintenance

This section outlines the process for upgrading the Chirpy theme and performing general maintenance.

### 4.1 Upgrading from Chirpy Starter

The website was created using `chirpy-starter`. Follow these steps to update the repository:

#### Preparation (One-time setup)
1.  **Adding Upstream:**
    ```bash
    git remote add chirpy https://github.com/cotes2020/chirpy-starter.git
    ```
    Verify with `git remote -v`.
2.  **Handling Submodule (`assets/lib`):**
    If `assets/lib` submodule is not required for your workflow, run:
    ```bash
    git config submodule.assets/lib.ignore all
    ```

#### Fetching Updates (For each update)
1.  Fetch all tags from upstream:
    ```bash
    git fetch chirpy --tags
    ```
2.  Merge the latest tag (e.g., `vX.Y.Z`) from upstream into your local branch:
    ```bash
    git merge vX.Y.Z --squash --allow-unrelated-histories
    ```
3.  **Resolve `assets/lib` conflicts:**
    *   If you do not want the submodule:
        ```bash
        git restore --staged assets/lib
        ```
    *   If you use the submodule, update it by merging the specified commit hash:
        ```bash
        git -C assets/lib merge <submodule_commit_hash>
        ```
4.  Resolve any other file conflicts manually, preserving custom modifications.
5.  Commit the upgrade:
    ```bash
    git add . && git commit -m "chore: upgrade to X.Y.Z"
    ```
6.  Update local theme gems:
    ```bash
    bundle update
    ```
