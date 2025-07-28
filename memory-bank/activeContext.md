# Active Context

## Current Work
Migrating blog posts from `D:\Git\LOFC-CM-202503.wiki` to the current blog (`d:/Git/alfred1137.github.io`). The migration plan has been drafted, accepted, and documented in the memory bank.

## Recent Changes
- Updated understanding of how to access the source repository: terminal tools can be used in Act Mode.
- Memory bank files (`activeContext.md`, `progress.md`) have been updated to reflect the latest plan and status.

## Next Steps
1.  Await user confirmation to switch to Act Mode to begin the migration process.

## Active Decisions and Considerations
- **Blog Post Filenames:** Source files include chapter titles (e.g., `Chapter-02-Progress-&-Redemption.md`).
- **Date Assignment:** Migrated posts will use the file creation date of the original source file.
- **Asset Handling:** Assets will be organized into post-specific folders within `assets/posts/<post-slug>/`.
- **Source Project Files:** `clinerules` and `memory-bank` from the source repository will be migrated, with a note to review for outdated instructions conflicting with the current blog's structure.
- **Source Repository Access:** Terminal tools will be used in Act Mode to access the source repository for file listing, content retrieval, and metadata.

## Important Patterns and Preferences
- Adherence to Jekyll blog structure (`_posts/`, `assets/`).
- Preference for organized asset management per blog post.

## Learnings and Project Insights
- Direct access to external file systems is not possible; user must provide file contents and metadata if terminal tools are insufficient or unavailable.
- Terminal tools can be leveraged in Act Mode to interact with the source repository.
- Careful handling of `clinerules` and `memory-bank` is required to avoid conflicts.
