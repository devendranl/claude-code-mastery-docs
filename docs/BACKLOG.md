# Product Backlog: Claude Code Mastery

## Priority Legend
- **P0:** Critical - Must fix immediately
- **P1:** High - Do in current sprint
- **P2:** Medium - Do soon
- **P3:** Low - Nice to have
- **P4:** Future - Consider later

## Status Legend
- [ ] Not started
- [~] In progress
- [x] Completed
- [-] Won't do

---

## P1: High Priority

### ~~BACK-001: Add README.md~~ ✅
**Type:** Documentation
**Priority:** P1
**Status:** COMPLETED (2026-02-01)

Created during Master Retrofit.

---

### ~~BACK-002: Add Meta Tags for SEO~~ ✅
**Type:** Improvement
**Priority:** P1
**Status:** COMPLETED (2026-02-01)

Added to index.html:
- [x] description meta tag
- [x] Open Graph tags (og:title, og:description, og:url, og:type, og:site_name)
- [x] Twitter card tags (card, url, title, description)
- [x] Canonical URL
- [x] Additional: keywords, author, robots, theme-color

---

### ~~BACK-003: Improve Mobile Touch Targets~~ ✅
**Type:** Accessibility
**Priority:** P1
**Status:** COMPLETED (2026-02-01)

Added touch target CSS for mobile/touch devices:
- [x] All buttons meet 44x44px minimum (menu-toggle, theme-toggle, logout-btn, copy-btn, login-btn)
- [x] Navigation links have min-height: 44px
- [x] Search results have proper padding (14px 16px)
- [x] Form inputs have min-height: 44px
- [x] Uses `@media (pointer: coarse)` for touch device detection

---

## P2: Medium Priority

### ~~BACK-004: Add Print Styles~~ ✅
**Type:** Feature
**Priority:** P2
**Status:** COMPLETED (2026-02-01)

Comprehensive print stylesheet added:
- [x] Hide header, sidebar, search, login overlay, copy buttons on print
- [x] Format content for paper (12pt font, black on white, proper margins)
- [x] Preserve code block formatting (pre-wrap, page-break-inside: avoid)
- [x] Page breaks at module boundaries (not first module)
- [x] Links show URLs in print
- [x] Orphans/widows control for paragraphs

---

### ~~BACK-005: Add Loading State~~ ✅
**Type:** UX Improvement
**Priority:** P2
**Status:** COMPLETED (2026-02-01)

Added loading overlay with spinner:
- [x] Show loading spinner on initial load (animated spinner + "Loading..." text)
- [x] Hide when libraries are ready (100ms check delay)
- [x] Graceful degradation if libraries fail (shows error message for 2s, then continues)

---

### ~~BACK-006: Keyboard Shortcuts Help~~ ✅
**Type:** Feature
**Priority:** P2
**Status:** COMPLETED (2026-02-01)

Added keyboard shortcuts modal:
- [x] `?` opens shortcuts modal
- [x] Lists all shortcuts organized by category (Navigation, Search Results, Appearance, Help)
- [x] `Escape` closes modal
- [x] Added new shortcuts: `/` to focus search, `t` to toggle theme
- [x] Click outside to close modal

---

### ~~BACK-007: Improve Code Block Accessibility~~ ✅
**Type:** Accessibility
**Priority:** P2
**Status:** COMPLETED (2026-02-01)

Enhanced code block accessibility:
- [x] Code blocks have `role="region"` and `aria-label="[language] code example"`
- [x] Language is announced via aria-label
- [x] Copy button has `aria-label="Copy [language] code to clipboard"`
- [x] Pre elements are keyboard focusable (`tabindex="0"`)
- [x] Focus styles for keyboard navigation

---

### ~~BACK-008: Add Scroll-to-Top Button~~ ✅
**Type:** UX Improvement
**Priority:** P2
**Status:** COMPLETED (2026-02-01)

Added floating scroll-to-top button:
- [x] Button appears after scrolling 500px
- [x] Smooth scroll to top on click
- [x] Button is accessible (aria-label, focus styles, keyboard accessible)
- [x] Doesn't obstruct content on mobile (positioned bottom-right, 44x44px on mobile)

---

## P3: Low Priority

### ~~BACK-009: Add Table of Contents in Main Content~~ ✅
**Type:** Feature
**Priority:** P3
**Status:** COMPLETED (2026-02-02)

Added floating table of contents:
- [x] Shows h2/h3 headings for current module section
- [x] Highlights current heading based on scroll position
- [x] Click to smooth scroll to heading
- [x] Hidden on screens <= 1200px (uses sidebar instead)
- [x] Dynamically updates when scrolling between sections

---

### ~~BACK-010: Add Estimated Reading Time~~ ✅
**Type:** Feature
**Priority:** P3
**Status:** COMPLETED (2026-02-02)

Added reading time estimates:
- [x] Calculate based on word count (200 words/min, excludes code blocks)
- [x] Display after module h1 heading
- [x] Format: "X min read" with clock icon

---

### ~~BACK-011: Add Progress Bar~~ ✅
**Type:** Feature
**Priority:** P3
**Status:** COMPLETED (2026-02-02)

Added reading progress bar:
- [x] Shows scroll position as percentage (width-based)
- [x] Smooth animation (CSS transition)
- [x] Visible but not distracting (3px height at bottom of header, accent color)

---

### ~~BACK-012: Syntax Theme Toggle~~ ✅
**Type:** Feature
**Priority:** P3
**Status:** COMPLETED (2026-02-02)

Added syntax theme selector:
- [x] Dropdown in header (hidden on mobile)
- [x] 5 theme options: Auto, GitHub Dark, GitHub Light, Monokai, Atom One Dark
- [x] "Auto" follows site theme (dark/light)
- [x] Persisted to localStorage

---

## P4: Future Considerations

### ~~BACK-013: Offline Support (Service Worker)~~ ✅
**Type:** Feature
**Priority:** P4
**Status:** COMPLETED (2026-02-02)

Added service worker for offline access:
- [x] Created sw.js with cache-first strategy
- [x] Precaches all CDN resources (highlight.js, fuse.js, themes)
- [x] Offline indicator shows when disconnected
- [x] Update notification when new version available
- [x] Automatic cache cleanup on version update

---

### ~~BACK-014: User Progress Tracking~~ ✅
**Type:** Feature
**Priority:** P4
**Status:** COMPLETED (2026-02-02)

Added user progress tracking:
- [x] Progress bar in sidebar showing X/9 modules completed
- [x] "Mark as Complete" button at end of each module
- [x] Visual indicator (green dot) on completed nav links
- [x] Progress persisted to localStorage

---

### BACK-015: Real Authentication
**Type:** Feature
**Priority:** P4
**Effort:** X-Large

**Description:**
Replace client-side auth with proper backend authentication.

---

### ~~BACK-016: Interactive Exercises~~ ✅
**Type:** Feature
**Priority:** P4
**Status:** COMPLETED (2026-02-02)

Added interactive exercises:
- [x] Exercise component with code editor textarea
- [x] Check Answer, Show Hint, Reset buttons
- [x] Validation with success/error feedback
- [x] Exercise 1: Configure settings.json
- [x] Exercise 2: Create a QA Agent definition

---

### ~~BACK-017: Multi-language Support~~ ✅
**Type:** Feature
**Priority:** P4
**Status:** COMPLETED (2026-02-02)

Added i18n framework:
- [x] Language selector in header (English, Español, 中文, 日本語)
- [x] Translation dictionary for UI strings
- [x] t() helper function for translations
- [x] Persisted language preference to localStorage
- [x] Updates key UI elements (search, logout, TOC, etc.)

---

## Completed Items

### BACK-C01: Convert Markdown to HTML
**Completed:** 2026-02-01
**Description:** Convert crash course markdown to interactive HTML documentation site.

### BACK-C02: Add Login Authentication
**Completed:** 2026-02-01
**Description:** Add gated access with test credentials.

### BACK-C03: Responsive Sidebar
**Completed:** 2026-02-01
**Description:** Make sidebar collapsible and work on all devices.

### BACK-C04: Master Retrofit
**Completed:** 2026-02-01
**Description:** Add Claude autonomy layer with agents, memory, and documentation.

---

## Technical Debt

### DEBT-001: Single File Size
**Priority:** P3
**Description:** index.html is 110KB+ and growing. May need to split if adding more features.
**Mitigation:** Consider static site generator if content doubles.

### DEBT-002: No Automated Tests
**Priority:** P2
**Description:** No automated testing exists.
**Mitigation:** Add Playwright E2E tests for critical paths.

### DEBT-003: Hardcoded Search Data
**Priority:** P3
**Description:** Search index is manually maintained in searchData array.
**Mitigation:** Generate from content programmatically.

---

## Notes

- Prioritization is based on user impact and effort
- P0/P1 items should be addressed before new features
- Technical debt should be addressed opportunistically
- Update this document as items are completed or priorities change
