<task name="Audit and Revise LOFC-CM Blog Posts">

<task_objective>
This workflow audits all LOFC-CM blog posts located in the `_posts/` directory to ensure they comply with the content and style guidelines defined in `.clinerules/01-content-creation-guide.md` and `.clinerules/lofc-cm-blog-guide.md`. It identifies non-compliant formatting, applies necessary revisions, and generates a summary report of all changes made.
</task_objective>

<detailed_sequence_steps>
# LOFC-CM Blog Post Audit Process - Detailed Sequence of Steps

## 1. Identify and Select Target Blog Post

1.  Use the `list_files` tool to get a list of all files in the `_posts/` directory.
2.  From the list, filter for all posts that contain "LOFC-CM" in their filename. These will be the candidate files for the audit.
3.  Present the list of candidate files to the user using the `ask_followup_question` tool, allowing them to choose which post to audit next.
4.  The following steps will be performed for the user-selected target file.

## 2. Audit and Document Non-Compliance

1.  Use the `read_file` tool to get the content of the user-selected post.

2.  Carefully audit the file's front matter and content against the rules in `01-content-creation-guide.md` and `lofc-cm-blog-guide.md`. Key checks include:
    -   **Front Matter**:
        -   `title`: Must follow the format `LOFC-CM-CH<chapter_number> | <Chapter_Title>` and must not contain colons.
        -   `categories`: Must be `["Gaming", "EA FC 2025", "LOFC-CM-2025"]`.
        -   `tags`: Must be `["Leyton Orient", "Career Mode", "LOFC-CM-2025"]`.
        -   `description`: Must not contain colons.
        -   `image` key: Must not be present in the front matter.
    -   **Content Body**:
        -   **Image Paths**: All image paths must be relative to `assets/img/` (e.g., `assets/img/LOFC-CM-CH01/image.png`). They must *not* use absolute GitHub Wiki URLs (e.g., `https://github.com/alfred1137/LOFC-CM-202503/wiki/Resources/`) or `mdc:` prefixes.
        -   **Image Sizing**: All images must include `w` and `h` attributes (e.g., `![alt text](/path/to/image.png){: w="700" h="400" }`).
        -   **Filepath Styling**: File paths should use the `filepath` class (e.g., ``/path/to/your/config.yml`{: .filepath}``).
        -   **Name Formatting**:
            -   Club names like `**Leyton Orient**` must be bold.
            -   Individual names like `*Dele Alli*` must be in italics.
            -   Manager name `*Filippo Inzaghi*` must be in italics.
        -   **Return to Homepage Link**: For all posts except `LOFC-CM-CH00`, a centered link `[Return to Homepage of the Leyton Orient Manager Career save](/posts/LOFC-CM-CH00/){: .align-center }` must be present at the very bottom of the file.

3.  Create a temporary list or internal log of all non-compliant issues found for the selected file. This will be used for generating the final report.

## 3. Apply Revisions to Non-Compliant Posts

1.  Based on the audit, use the `replace_in_file` tool to correct any identified issues in the selected file.
    -   Create specific `SEARCH/REPLACE` blocks for each correction needed.
    -   If a file has multiple issues, multiple `SEARCH/REPLACE` blocks can be used in a single `replace_in_file` call.
    -   If `replace_in_file` fails repeatedly, fall back to reading the file with `read_file` and overwriting it with the corrected content using `write_to_file`.

## 4. Generate Audit Report for Selected Post

1.  After auditing the selected post, create a new Markdown file named `outputs/lofc-cm-audit-report-YYYY-MM-DD.md` using the `write_to_file` tool. The tool will automatically create the `outputs/` directory if it does not exist.

2.  Write the audit findings to the report file. The report should be structured as follows:
    -   A summary of the audit for the selected post.
    -   The name of the file that was scanned.
    -   A detailed breakdown of the specific changes made (e.g., "Corrected title format", "Fixed image path", "Standardized tags").

4.  Use the `attempt_completion` tool to present the final audit report to the user.

</detailed_sequence_steps>

</task>
