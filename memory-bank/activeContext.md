# Active Context

## Current Work
Migrating blog posts from `D:\Git\LOFC-CM-202503.wiki` to the current blog (`d:/Git/alfred1137.github.io`). The migration plan has been drafted, accepted, and documented in the memory bank.

## Recent Changes
- Updated understanding of how to access the source repository: terminal tools can be used in Act Mode.
- Memory bank files (`activeContext.md`, `progress.md`) have been updated to reflect the latest plan and status.
- Chapter 00 (Home Page) has been created as `_posts/2025-03-06-LOFC-CM-CH00.md`. (Corrected filename)
- The banner image has been copied to `assets/img/LOFC-CM-00/Banner.png` and its path updated in the post.

## Next Steps
1.  Process Blog Posts (Iterative): For each subsequent chapter markdown file, migrate content and assets, awaiting user acceptance for each chapter.
2.  Migrate Configuration Directories: Merge `clinerules` and `memory-bank` from `migration_temp` into the project root, prioritizing existing files.
3.  Review and Refine: Address any conflicts or issues found in migrated project-specific files.
4.  Cleanup: Delete the copied source repository once the user confirms satisfaction with the entire migration.

## Active Decisions and Considerations
- **Blog Post Filenames:** Source files include chapter titles (e.g., `Chapter-02-Progress-&-Redemption.md`). The correct Jekyll format `YYYY-MM-DD-TITLE.md` must be strictly followed. The prefix `LOFC-CM-` should not be part of the filename itself but rather handled within the content or title if necessary. The corrected filename for Chapter 00 is `_posts/2025-03-06-LOFC-CM-CH00.md`.
- **Date Assignment:** Migrated posts will use the file creation date of the original source file.
- **Asset Handling:** Assets will be organized into post-specific folders within `assets/img/LOFC-CM-CH00/` for Chapter 00, and `assets/img/LOFC-CM-<chapter_number>/` for subsequent chapters.
- **Source Project Files:** `clinerules` and `memory-bank` from the source repository will be migrated, with a note to review for outdated instructions conflicting with the current blog's structure.
- **Source Repository Access:** Terminal tools will be used in Act Mode to access the source repository for file listing, content retrieval, and metadata.

## Important Patterns and Preferences
- Adherence to Jekyll blog structure (`_posts/`, `assets/`).
- Preference for organized asset management per blog post.

## Learnings and Project Insights
- User feedback on image paths is critical. External images from specific sources (like GitHub wiki) should be migrated to local assets, while others should remain external.
- The `write_to_file` tool's output includes user edits, and the `final_file_content` should be used as the reference for subsequent operations.
- Terminal tools can be leveraged in Act Mode to interact with the source repository.
- Careful handling of `clinerules` and `memory-bank` is required to avoid conflicts.
- **File Naming Convention:** Strict adherence to Jekyll's `YYYY-MM-DD-TITLE.md` format is crucial for blog post filenames. Custom prefixes like `LOFC-CM-` should not be part of the filename itself but handled within the content or title if necessary. The "Chapter 00" identifier should be clearly represented in the title.
