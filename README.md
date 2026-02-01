# Claude Code Mastery

Interactive documentation site for the **Claude Code CLI Mastery: Autonomous Product Development** crash course.

**Live Site:** [https://claudetutor.vercel.app](https://claudetutor.vercel.app)

## Overview

This site teaches developers how to use Claude Code CLI as an autonomous development partner. The crash course covers:

- **Core Philosophy** - Mental model shift from tool use to strategic delegation
- **CLI Fundamentals** - Installation, commands, and context loading
- **Configuration** - CLAUDE.md, settings.json, autonomy modes
- **Agent Architecture** - Specialized personas for different tasks
- **Autonomous Development** - Full workflow from idea to shipped product
- **MCP & Extensions** - Model Context Protocol and tool integration
- **Product Delivery** - Full-stack development, testing, CI/CD
- **Marketing & GTM** - Landing pages, pitch decks, content strategy
- **Reference Templates** - Ready-to-use templates and patterns

## Features

- Full-text search (Cmd+K)
- Syntax highlighted code blocks with copy button
- Dark/light mode toggle
- Collapsible sidebar navigation
- Mobile responsive design
- Login-gated access

## Tech Stack

- **Frontend:** Vanilla HTML, CSS, JavaScript
- **Libraries:** Highlight.js (syntax highlighting), Fuse.js (search)
- **Hosting:** Vercel (static)

## Development

### Prerequisites
- Git
- Vercel CLI (optional, for deployment)

### Local Development

1. Clone the repository:
   ```bash
   git clone https://github.com/devendranl/claude-code-mastery-docs.git
   cd claude-code-mastery-docs
   ```

2. Open `index.html` in a browser:
   ```bash
   open index.html
   ```

   Or use a local server:
   ```bash
   npx serve .
   ```

3. Login with test credentials:
   - Email: `test@claude.ai`
   - Password: `mastery2025`

### Making Changes

All code is in `index.html`:
- HTML structure at the top
- CSS in `<style>` tag
- JavaScript in `<script>` tag at bottom

### Deployment

Deploy to Vercel:
```bash
vercel --prod
```

Or push to main branch (if Vercel GitHub integration is set up).

## Project Structure

```
claude-code-mastery-docs/
├── CLAUDE.md                    # Claude Code quick reference
├── README.md                    # This file
├── index.html                   # Main application
├── claude-code-mastery-crash-course.md  # Source content
├── .claude/
│   ├── CLAUDE.md                # Detailed Claude instructions
│   ├── settings.json            # Configuration
│   ├── agents/                  # Agent definitions
│   ├── memory/                  # Session state
│   └── templates/               # Document templates
└── docs/
    ├── PRD.md                   # Product requirements
    ├── ARCHITECTURE.md          # System design
    └── BACKLOG.md               # Prioritized work items
```

## Claude Code Integration

This project is set up for Claude Code CLI autonomous development:

```bash
# Start a Claude session
claude

# Claude will read CLAUDE.md and understand the project
# Then you can give instructions like:
claude "Add a scroll-to-top button"
claude "Fix the mobile layout issue"
claude "Improve the search results UI"
```

See `.claude/CLAUDE.md` for detailed instructions on how Claude should work with this project.

## Contributing

1. Check `docs/BACKLOG.md` for prioritized work items
2. Make changes to `index.html`
3. Test on desktop, tablet, and mobile
4. Test dark and light modes
5. Commit with descriptive message
6. Deploy with `vercel --prod`

## License

MIT

## Acknowledgments

- [Highlight.js](https://highlightjs.org/) for syntax highlighting
- [Fuse.js](https://fusejs.io/) for fuzzy search
- [Vercel](https://vercel.com/) for hosting
