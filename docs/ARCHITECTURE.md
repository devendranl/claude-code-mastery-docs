# Architecture Document: Claude Code Mastery

## System Overview

Claude Code Mastery is a single-page static documentation site. The entire application lives in one HTML file with inline CSS and JavaScript, deployed to Vercel's edge network.

```
┌─────────────────────────────────────────────────────────────────┐
│                        ARCHITECTURE                              │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│  ┌────────────────────────────────────────────────────────────┐ │
│  │                     index.html                              │ │
│  │  ┌──────────────────────────────────────────────────────┐  │ │
│  │  │                     <head>                            │  │ │
│  │  │  • Meta tags (SEO, viewport)                          │  │ │
│  │  │  • CDN links (Highlight.js, Fuse.js)                  │  │ │
│  │  │  • <style> - All CSS (~2000 lines)                    │  │ │
│  │  └──────────────────────────────────────────────────────┘  │ │
│  │  ┌──────────────────────────────────────────────────────┐  │ │
│  │  │                     <body>                            │  │ │
│  │  │  • Login overlay                                      │  │ │
│  │  │  • Header (logo, search, theme, logout)               │  │ │
│  │  │  • Sidebar (navigation)                               │  │ │
│  │  │  • Main (content sections)                            │  │ │
│  │  │  • Search modal                                       │  │ │
│  │  │  • <script> - All JavaScript (~500 lines)             │  │ │
│  │  └──────────────────────────────────────────────────────┘  │ │
│  └────────────────────────────────────────────────────────────┘ │
│                              │                                   │
│                              ▼                                   │
│  ┌────────────────────────────────────────────────────────────┐ │
│  │                   CDN Dependencies                          │ │
│  │  ┌─────────────────────┐  ┌─────────────────────────────┐  │ │
│  │  │    Highlight.js     │  │         Fuse.js             │  │ │
│  │  │  • Core library     │  │  • Search library            │  │ │
│  │  │  • TypeScript       │  │  • Fuzzy matching            │  │ │
│  │  │  • Bash             │  │                              │  │ │
│  │  │  • JSON             │  │                              │  │ │
│  │  │  • YAML             │  │                              │  │ │
│  │  │  • Markdown         │  │                              │  │ │
│  │  └─────────────────────┘  └─────────────────────────────┘  │ │
│  └────────────────────────────────────────────────────────────┘ │
│                              │                                   │
│                              ▼                                   │
│  ┌────────────────────────────────────────────────────────────┐ │
│  │                      Vercel                                 │ │
│  │  • Static file hosting                                      │ │
│  │  • Edge network (global CDN)                                │ │
│  │  • HTTPS                                                    │ │
│  │  • https://claudetutor.vercel.app                           │ │
│  └────────────────────────────────────────────────────────────┘ │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

## Component Architecture

### HTML Structure
```html
<body data-theme="dark">
  <!-- Layer 1: Login Gate -->
  <div class="login-overlay" id="loginOverlay">
    <div class="login-container">
      <form class="login-form">...</form>
    </div>
  </div>

  <!-- Layer 2: Application -->
  <div class="app-content" id="appContent">

    <!-- Header Bar -->
    <header class="header">
      <button class="menu-toggle">...</button>
      <div class="logo">...</div>
      <button class="search-trigger">...</button>
      <button class="theme-toggle">...</button>
      <button class="logout-btn">...</button>
    </header>

    <!-- Sidebar Overlay (mobile) -->
    <div class="sidebar-overlay"></div>

    <!-- Navigation Sidebar -->
    <nav class="sidebar" id="sidebar">
      <div class="nav-section">...</div>
      <!-- repeated for each module -->
    </nav>

    <!-- Search Modal -->
    <div class="search-modal" id="searchModal">...</div>

    <!-- Main Content -->
    <main class="main">
      <section class="section" id="module-1">...</section>
      <!-- repeated for each section -->
    </main>
  </div>
</body>
```

### CSS Architecture

```css
/* 1. Custom Properties (Variables) */
:root {
  --bg-primary: #0d1117;
  --text-primary: #e6edf3;
  /* ... theme variables */
}

[data-theme="light"] {
  --bg-primary: #ffffff;
  /* ... light theme overrides */
}

/* 2. Reset & Base Styles */
* { margin: 0; padding: 0; box-sizing: border-box; }
body { font-family: ...; background: var(--bg-primary); }

/* 3. Layout Components */
.header { position: fixed; ... }
.sidebar { position: fixed; ... }
.main { margin-left: var(--sidebar-width); ... }

/* 4. UI Components */
.button { ... }
.code-block { ... }
.search-modal { ... }

/* 5. State Modifiers */
.sidebar-open .sidebar { transform: translateX(0); }
.login-overlay.hidden { display: none; }

/* 6. Responsive Breakpoints */
@media (max-width: 1024px) { ... }
@media (max-width: 768px) { ... }
@media (max-width: 480px) { ... }
```

### JavaScript Architecture

```javascript
// 1. Configuration & Data
const TEST_USER = { email: '...', password: '...' };
const searchData = [ { id, title, content }, ... ];

// 2. Initialization
const fuse = new Fuse(searchData, options);
checkAuth();
initSidebar();
hljs.highlightAll();

// 3. Core Functions
function toggleTheme() { ... }
function toggleSidebar() { ... }
function openSearch() / closeSearch() { ... }
function performSearch(query) { ... }
function handleLogin(event) { ... }
function handleLogout() { ... }
function copyCode(btn) { ... }

// 4. Event Listeners
document.addEventListener('keydown', ...);  // Cmd+K, Escape, Arrow keys
document.getElementById('searchInput').addEventListener('input', ...);
// Intersection Observer for active section
```

## Data Flow

### Authentication Flow
```
┌──────────┐     ┌──────────────┐     ┌─────────────┐
│  User    │────▶│  Login Form  │────▶│  Validate   │
└──────────┘     └──────────────┘     └─────────────┘
                                            │
                    ┌───────────────────────┴───────────────────────┐
                    │                                               │
                    ▼                                               ▼
            ┌─────────────┐                                 ┌─────────────┐
            │   Success   │                                 │   Failure   │
            │  Store in   │                                 │ Show Error  │
            │ localStorage│                                 └─────────────┘
            └─────────────┘
                    │
                    ▼
            ┌─────────────┐
            │ Show App    │
            │  Content    │
            └─────────────┘
```

### Search Flow
```
┌──────────┐     ┌──────────────┐     ┌─────────────┐
│  Cmd+K   │────▶│ Open Modal   │────▶│ Focus Input │
└──────────┘     └──────────────┘     └─────────────┘
                                            │
                                            ▼
┌──────────┐     ┌──────────────┐     ┌─────────────┐
│  Type    │────▶│ Fuse.search  │────▶│ Render      │
│  Query   │     │   (fuzzy)    │     │  Results    │
└──────────┘     └──────────────┘     └─────────────┘
                                            │
                                            ▼
┌──────────┐     ┌──────────────┐     ┌─────────────┐
│  Select  │────▶│ Navigate to  │────▶│ Close Modal │
│  Result  │     │   Section    │     │             │
└──────────┘     └──────────────┘     └─────────────┘
```

### Theme Toggle Flow
```
┌──────────┐     ┌──────────────┐     ┌─────────────┐
│  Click   │────▶│ Toggle       │────▶│ Update CSS  │
│  Toggle  │     │ data-theme   │     │ Variables   │
└──────────┘     └──────────────┘     └─────────────┘
                       │
                       ▼
                ┌─────────────┐
                │   Save to   │
                │ localStorage│
                └─────────────┘
```

## State Management

### Client-Side State (localStorage)
| Key | Purpose | Values |
|-----|---------|--------|
| `claudeMasteryAuth` | Login state | `"true"` or absent |
| `theme` | Theme preference | `"dark"` or `"light"` |
| `sidebarOpen` | Sidebar state (desktop) | `"true"` or `"false"` |

### DOM State (Classes)
| Class | Element | Purpose |
|-------|---------|---------|
| `sidebar-open` | `body` | Sidebar visibility |
| `active` | `.nav-link` | Current section |
| `hidden` | `.login-overlay` | Hide login screen |
| `visible` | `.app-content` | Show main app |

## External Dependencies

| Dependency | Version | Purpose | Fallback |
|------------|---------|---------|----------|
| Highlight.js | 11.9.0 | Syntax highlighting | Code displays unstyled |
| Fuse.js | 7.0.0 | Fuzzy search | Search non-functional |

### CDN URLs
```
https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/
https://cdnjs.cloudflare.com/ajax/libs/fuse.js/7.0.0/
```

## Security Considerations

### Current Model
- **Authentication:** Client-side only (not secure for sensitive data)
- **Credentials:** Hardcoded in JavaScript (visible in source)
- **Transport:** HTTPS via Vercel
- **No Backend:** No API keys, secrets, or server-side vulnerabilities

### Limitations
- Anyone can view source and find credentials
- No rate limiting on login attempts
- No session expiration
- Suitable for: Gated content, not sensitive data

### If Security Upgrade Needed
1. Add backend authentication service
2. Use secure session tokens
3. Implement proper password hashing
4. Add rate limiting and lockout

## Performance Characteristics

### Initial Load
- Single HTML file (~110KB)
- Two CSS files from CDN (~20KB each)
- Two JS files from CDN (~50KB total)
- **Total:** ~200KB, single round-trip for HTML

### Runtime Performance
- No framework overhead
- Direct DOM manipulation
- Intersection Observer for scroll tracking
- Debounced search on input

### Optimization Opportunities
- Lazy-load syntax highlighting for non-visible code
- Service worker for offline access
- Image optimization (if images added)
- Critical CSS inlining (already done)

## Deployment Architecture

```
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│    Developer    │     │     GitHub      │     │     Vercel      │
│                 │────▶│                 │────▶│                 │
│  git push       │     │    main branch  │     │  Build & Deploy │
└─────────────────┘     └─────────────────┘     └─────────────────┘
                                                        │
                        ┌───────────────────────────────┘
                        │
                        ▼
        ┌───────────────────────────────────────┐
        │           Vercel Edge Network          │
        │                                        │
        │  ┌────────┐  ┌────────┐  ┌────────┐  │
        │  │  SFO   │  │  IAD   │  │  AMS   │  │
        │  └────────┘  └────────┘  └────────┘  │
        │       ▲           ▲           ▲      │
        └───────┼───────────┼───────────┼──────┘
                │           │           │
        ┌───────┴───────────┴───────────┴──────┐
        │              Users (Global)           │
        └──────────────────────────────────────┘
```

## Future Architecture Considerations

### If Adding Backend
- Consider Vercel Edge Functions
- Or separate API service
- Would enable: real auth, analytics, user data

### If Scaling Content
- Consider static site generator (11ty, Astro)
- Would enable: multiple HTML files, better maintainability
- Trade-off: adds build step

### If Adding Interactivity
- Consider lightweight framework (Preact, Alpine.js)
- Would enable: reactive UI, component reuse
- Trade-off: increases complexity
