<task name="Audit and Revise LOFC-CM Blog Posts">

<task_objective>
This workflow audits all LOFC-CM blog posts located in the `_posts/` directory to ensure they comply with the content and style guidelines defined in `.clinerules/01-content-creation-guide.md` and `.clinerules/lofc-cm-blog-guide.md`. It identifies non-compliant formatting, applies necessary revisions, and generates a summary report of all changes made.
</task_objective>

<detailed_sequence_steps>
# LOFC-CM Blog Post Audit Process - Detailed Sequence of Steps

## 1. Select Target Blog Post

1.  Use the `ask_followup_question` tool to prompt the user to select a specific LOFC-CM blog post from the `_posts/` directory to audit.
    -   Provide a list of all `LOFC-CM` posts as options.

## 2. Audit and Document Non-Compliance

1.  For each identified post, use the `read_file` tool to get its content.

2.  Carefully audit the file's front matter and content against the rules in `01-content-creation-guide.md` and `lofc-cm-blog-guide.md`. Key checks include:
    -   **Front Matter**:
        -   `title`: Must follow the format `LOFC-CM-CH<chapter_number> | <Chapter_Title>` and must not contain colons.
        -   `categories`: Must be `["Gaming", "EA FC 2025", "LOFC-CM-2025"]`.
        -   `tags`: Must be `["Leyton Orient", "Career Mode", "LOFC-CM-2025"]`.
        -   `description`: Must not contain colons.
        -   `image` key: Must not be present in the front matter.
    -   **Content Body**:
        -   **Image Paths**: All image paths must be relative to `assets/img/` (e.g., `assets/img/LOFC-CM-CH01/image.png`) and not absolute local paths.
        -   **Name Formatting**:
            -   Club names like `**Leyton Orient**` must be bold.
            -   Individual names like `*Dele Alli*` must be in italics.
            -   Manager name `*Filippo Inzaghi*` must be in italics.

3.  Create a temporary list or internal log of all non-compliant issues found for each file. This will be used for generating the final report.

## 3. Apply Revisions to Non-Compliant Posts

1.  Based on the audit, use the `replace_in_file` tool to correct any identified issues in each file.
    -   Create specific `SEARCH/REPLACE` blocks for each correction needed.
    -   If a file has multiple issues, multiple `SEARCH/REPLACE` blocks can be used in a single `replace_in_file` call.
    -   If `replace_in_file` fails repeatedly, fall back to reading the file with `read_file` and overwriting it with the corrected content using `write_to_file`.

## 4. Generate Final Audit Report

1.  Check if the `outputs/` directory exists. If not, create it.

2.  Create a new Markdown file named `outputs/lofc-cm-audit-report-YYYY-MM-DD.md`.

3.  Write the audit findings to the report file. The report should be structured as follows:
    -   A summary of the audit.
    -   A list of all files that were scanned.
    -   A detailed breakdown for each file that was modified, showing the specific changes made (e.g., "Corrected title format", "Fixed image path", "Standardized tags").

4.  Use the `attempt_completion` tool to present the final audit report to the user.

</detailed_sequence_steps>

</task>
