# Active Context

## Current Work
Migrating blog posts from `D:\Git\LOFC-CM-202503.wiki` to the current blog (`d:/Git/alfred1137.github.io`). The migration plan has been drafted, accepted, and documented in the memory bank. Chapter 00, Chapter 01, Chapter 02, Chapter 03, Chapter 04, Chapter 05, Chapter 06, Chapter 07, Chapter 08, Chapter 09, Chapter 10, Chapter 11, and Chapter 12 have been successfully migrated, deployed, and all identified `html-proofer` errors have been resolved.

## Recent Changes
- The file `_posts/2025-03-06-LOFC-CM-CH00.md` has been confirmed as the correct file for Chapter 00.
- The banner image has been correctly placed at `assets/img/LOFC-CM-CH00/Banner.png`.
- The external link `www.leytonorient.com` has been corrected to include the `https://` protocol.

- The file `_posts/2025-04-03-LOFC-CM-CH05.md` has been migrated with the correct title, description metadata, and assets.
- The file `_posts/2025-04-08-LOFC-CM-CH07.md` has been migrated with the correct title, description metadata, and assets.
- Memory bank files (`progress.md`, `activeContext.md`) have been updated to reflect the latest status and learnings.

- The file `_posts/2025-06-18-LOFC-CM-CH10-Season-3-Prologue.md` has been migrated with the correct title, description metadata, and assets.
- The file `_posts/2025-06-23-LOFC-CM-CH11.md` has been migrated with the correct title, description metadata, and assets.
- The file `_posts/2025-07-26-LOFC-CM-CH12-S3-Half-Season-Review-Winter-Transfer.md` has been migrated with the correct title, description metadata, and assets.

## Next Steps
1.  **Migrate Configuration Directories:** Merge `clinerules` and `memory-bank` from `migration_temp` into the project root, prioritizing existing files.
2.  **Review and Refine:** Address any conflicts or issues found in migrated project-specific files.
3.  **Cleanup:** Delete the copied source repository once the user confirms satisfaction with the entire migration.

## Active Decisions and Considerations
- **Blog Post Filenames:** Source files include chapter titles (e.g., `Chapter-02-Progress-&-Redemption.md`). The correct Jekyll format `YYYY-MM-DD-TITLE.md` must be strictly followed. The prefix `LOFC-CM-` should not be part of the filename itself but rather handled within the content or title if necessary. The corrected filename for Chapter 00 is `_posts/2025-03-06-LOFC-CM-CH00.md`.
- **Asset Handling:** Assets will be organized into post-specific folders within `assets/img/LOFC-CM-CH00/` for Chapter 00, and `assets/img/LOFC-CM-<chapter_number>/` for subsequent chapters.
- **Source Project Files:** `clinerules` and `memory-bank` from the source repository will be migrated, with a note to review for outdated instructions conflicting with the current blog's structure.
- **Source Repository Access:** Terminal tools will be used in Act Mode to access the source repository for file listing, content retrieval, and metadata.

## Important Patterns and Preferences
- Adherence to Jekyll blog structure (`_posts/`, `assets/`).
- Preference for organized asset management per blog post.
- **Standardized Categories and Tags for Migrated Posts:** For all posts migrated as part of this exercise, the following categories and tags will be used:
    - Categories: `["Gaming", "EA FC 2025", "LOFC-CM-2025"]`
    - Tags: `["Leyton Orient", "Career Mode", "LOFC-CM-2025"]`
- **Standardized Title Format for Chapters:** For all blog posts migrated as part of this exercise, the `title` metadata should follow the convention: `LOFC-CM-CH<chapter_number> | <Original Chapter Title>`. `:` is strictly forbidden here.
- **Standardized Description for Posts:** For all blog posts migrated as part of this exercise, the `description` metadata should be generated as a concise summary of the blog content. `:` is strictly forbidden here.
- **Title Format Rule:** Colons (`:`) are not allowed in post titles. Use hyphens (`-`) or pipes (`|`) as separators instead.
- Do not include `image` in metadata.

## Learnings and Project Insights
- **File Naming:** The correct Jekyll filename format `YYYY-MM-DD-TITLE.md` is crucial. The correct path for Chapter 00's image is `assets/img/LOFC-CM-CH00/Banner.png`, not `assets/img/LOFC-CM-00/Banner.png` as initially suggested by an `html-proofer` error.
- **External Link Formatting:** `html-proofer` requires external links to include a protocol (e.g., `https://`) to be correctly recognized. The link `www.leytonorient.com` was corrected to `https://www.leytonorient.com`.
- **Tool Limitations and User Collaboration:** When direct file modification is denied, the process involves:
    1.  Identifying the issue and required changes.
    2.  Reading the relevant file content.
    3.  Clarifying discrepancies with the user (e.g., file paths).
    4.  Providing the user with corrected content or instructions for them to apply.
    5.  Asking the user to confirm the changes and re-run checks.
- **Current State:** Chapter 00, Chapter 01, Chapter 02, Chapter 03, Chapter 04, Chapter 05, Chapter 06, Chapter 07, Chapter 08, Chapter 09, Chapter 10, Chapter 11, and Chapter 12 are migrated, deployed, and all identified `html-proofer` errors are resolved. The fix for missing image alt attributes has been verified through successful redeployment.
- **Lesson Learned:** Ensure all images within post content have descriptive `alt` attributes for accessibility and to prevent deployment errors, even if not explicitly detailed in all theme guides.
- **Next Steps:** Proceed with migrating subsequent blog posts (Step 2 of the plan), starting with Chapter 12.
