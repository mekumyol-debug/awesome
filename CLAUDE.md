# CLAUDE.md

## Project Overview

This is the **[Awesome](https://awesome.re)** meta-list — the curated directory of all awesome lists on GitHub. It is maintained by Sindre Sorhus and the community. The repository is **not a code project**; it is a Markdown-based curation of links to high-quality "awesome-*" repositories organized by topic.

- **License:** CC0 1.0 Universal (public domain)
- **Primary file:** `readme.md` — the main list (~930 lines of categorized links)
- **Website:** [awesome.re](https://awesome.re)

## Repository Structure

```
.
├── readme.md                  # The main awesome list (all curated entries)
├── awesome.md                 # Manifesto — what "awesome" means, badge info
├── contributing.md            # Contribution guidelines for adding lists
├── create-list.md             # Instructions for creating new awesome lists
├── pull_request_template.md   # PR checklist (40+ items, very strict)
├── code-of-conduct.md         # Contributor Covenant v1.4
├── license                    # CC0 1.0
├── media/                     # Logos, badges, and visual assets (SVG, PNG, AI, Sketch)
├── .editorconfig              # Tabs, LF, UTF-8, trim whitespace, final newline
├── .gitattributes             # Auto LF normalization, union merge for readme.md
└── .github/
    └── workflows/
        ├── main.yml           # GitHub Actions CI — runs on PRs to main touching readme.md
        └── repo_linter.sh     # Extracts new list URLs from diff and runs awesome-lint
```

## Key Files

| File | Purpose |
|------|---------|
| `readme.md` | The canonical awesome list. All curated entries live here, organized into ~25 categories (Platforms, Programming Languages, Front-End Development, etc.) with a `Contents` table of contents at the top. |
| `pull_request_template.md` | Extensive checklist that all PR submitters must follow. Read this before making any changes to `readme.md`. |
| `awesome.md` | The manifesto: only include genuinely awesome items, badge usage rules, style guidance. |
| `.github/workflows/repo_linter.sh` | CI script: extracts newly added `https://...#readme` links from the diff, clones the linked repo, and runs `npx awesome-lint` on it. |

## Formatting Conventions

### Entry Format

Each list entry follows this pattern:

```md
- [Name of List](https://github.com/user/awesome-name#readme) - Short description starting with uppercase, ending with a period.
```

- **Link text:** Title-cased name (e.g., `Node.js`, not `NodeJS` or `node.js`)
- **URL:** Must end in `#readme`
- **Separator:** ` - ` (space-dash-space) between the link and description
- **Description:** Starts uppercase, ends with `.`, describes the project/theme (not the list itself), does not repeat the list name
- **Placement:** New entries go at the bottom of the appropriate category
- Sub-entries are indented with a tab

### Markdown Style

- Use **tabs** for indentation (per `.editorconfig`)
- Line endings: **LF** (Unix-style)
- Charset: **UTF-8**
- Trim trailing whitespace
- Insert final newline
- **No hard-wrapping** — let lines be as long as needed
- No CI badges in awesome lists

## CI/CD

- **Trigger:** Pull requests to `main` that modify `readme.md`
- **Action:** `.github/workflows/main.yml` runs `repo_linter.sh`
- **What it does:** Finds newly added repository URLs (`https://...#readme`) in the diff, clones the target repo, and runs `npx awesome-lint` to validate compliance
- **No other CI** — there are no test suites, build steps, or package managers

## Contribution Rules

These are critical — PRs that don't follow them get closed:

1. **PR title format:** `Add Name of List` — no "Awesome" prefix, no lowercase, no past tense
2. **No AI-generated content** — fully AI-generated PRs are rejected
3. **Reviewers must review 4 other open PRs** with substantive feedback before submitting
4. **30-day maturity requirement** — the linked awesome list must have existed for at least 30 days
5. **No blockchain-related lists**
6. **No duplicates** — search existing entries first
7. **Linked list requirements:**
   - Default branch named `main`
   - Has `awesome-list` and `awesome` GitHub topics
   - Includes Awesome badge, Table of Contents (named `Contents`), contribution guidelines (`contributing.md`), and appropriate license (CC0 recommended)
   - Passes `awesome-lint`
   - Repo name in lowercase slug format: `awesome-name-of-list`

## Git Conventions

- **Default branch:** `main`
- **Merge strategy for `readme.md`:** Union merge (`.gitattributes`) to reduce conflicts
- **Commit messages:** Short, descriptive (e.g., `Add Swift`, `Remove broken link`, `Meta tweaks`)
- **Binary files:** `.ai` files are marked as binary in `.gitattributes`

## Common Tasks

### Adding a new list entry

1. Edit `readme.md`
2. Find the correct category section
3. Add the entry at the **bottom** of that category
4. Follow the exact format: `- [Title Case Name](https://github.com/user/repo#readme) - Description with uppercase start and period at end.`
5. Ensure the linked repository passes `awesome-lint`

### Updating an existing entry

1. Find the entry in `readme.md`
2. Verify the new URL/description follows all formatting conventions
3. Keep the entry in the same category position unless it needs recategorization

### Running the linter locally

```sh
# On a specific awesome list repo (not this repo):
npx awesome-lint
```

The linter runs automatically via CI on PRs that modify `readme.md`.

## Categories in readme.md

The list is organized into these top-level sections (in order):

Platforms, Programming Languages, Front-End Development, Back-End Development, Computer Science, Big Data, Theory, Books, Editors, Gaming, Development Environment, Entertainment, Databases, Media, Learn, Security, Content Management Systems, Hardware, Business, Work, Networking, Decentralized Systems, Health and Social Science, Events, Testing, Miscellaneous, Related
