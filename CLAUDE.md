# Project: Claude Code Mastery

> Quick reference for Claude Code sessions. See `.claude/CLAUDE.md` for detailed instructions.

## Product Overview
Interactive documentation site for the "Claude Code CLI Mastery: Autonomous Product Development" crash course. A single-page application with authentication, full-text search, syntax highlighting, and responsive design.

**Live URL:** https://claudetutor.vercel.app

## Tech Stack
- **Frontend:** Vanilla HTML/CSS/JavaScript (single-page app)
- **Libraries:** Highlight.js (syntax highlighting), Fuse.js (search)
- **Deployment:** Vercel (static hosting)
- **Version Control:** Git + GitHub

## Key Files
| File | Purpose |
|------|---------|
| `index.html` | Main application (all HTML, CSS, JS in one file) |
| `claude-code-mastery-crash-course.md` | Source content for the documentation |

## Quick Commands
```bash
# Deploy to production
vercel --prod

# Push changes
git add . && git commit -m "message" && git push origin main
```

## Current Priority
See `docs/BACKLOG.md` for prioritized work items.

## Decision Authority
- **Autonomous:** UI tweaks, bug fixes, content updates, styling changes
- **Requires Approval:** Auth changes, new features, structural changes, external integrations
