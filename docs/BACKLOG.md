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

### BACK-003: Improve Mobile Touch Targets
**Type:** Accessibility
**Priority:** P1
**Effort:** Small

**Description:**
Ensure all touch targets (buttons, links) are at least 44x44px on mobile for better accessibility.

**Acceptance Criteria:**
- [ ] All buttons meet size requirement
- [ ] Navigation links are easy to tap
- [ ] Search results are tappable

---

## P2: Medium Priority

### BACK-004: Add Print Styles
**Type:** Feature
**Priority:** P2
**Effort:** Small

**Description:**
Improve print stylesheet so users can print individual sections or the full document.

**Acceptance Criteria:**
- [ ] Hide header, sidebar, search on print
- [ ] Format content for paper
- [ ] Preserve code block formatting
- [ ] Page breaks at section boundaries

---

### BACK-005: Add Loading State
**Type:** UX Improvement
**Priority:** P2
**Effort:** Small

**Description:**
Add a loading indicator while external libraries (Highlight.js, Fuse.js) load.

**Acceptance Criteria:**
- [ ] Show loading spinner on initial load
- [ ] Hide when libraries are ready
- [ ] Graceful degradation if libraries fail

---

### BACK-006: Keyboard Shortcuts Help
**Type:** Feature
**Priority:** P2
**Effort:** Medium

**Description:**
Add a keyboard shortcuts modal (activated by `?` key) showing available shortcuts.

**Acceptance Criteria:**
- [ ] `?` opens shortcuts modal
- [ ] Lists: Cmd+K (search), / (focus search), t (toggle theme)
- [ ] Escape closes modal

---

### BACK-007: Improve Code Block Accessibility
**Type:** Accessibility
**Priority:** P2
**Effort:** Medium

**Description:**
Add proper ARIA labels and roles to code blocks for screen reader users.

**Acceptance Criteria:**
- [ ] Code blocks have role="code"
- [ ] Language is announced
- [ ] Copy button has aria-label

---

### BACK-008: Add Scroll-to-Top Button
**Type:** UX Improvement
**Priority:** P2
**Effort:** Small

**Description:**
Add a floating button to scroll back to top when user has scrolled down.

**Acceptance Criteria:**
- [ ] Button appears after scrolling 500px
- [ ] Smooth scroll to top on click
- [ ] Button is accessible
- [ ] Doesn't obstruct content on mobile

---

## P3: Low Priority

### BACK-009: Add Table of Contents in Main Content
**Type:** Feature
**Priority:** P3
**Effort:** Medium

**Description:**
Add a floating table of contents for the current section showing sub-sections.

**Acceptance Criteria:**
- [ ] Shows headings for current module
- [ ] Highlights current position
- [ ] Click to navigate
- [ ] Hidden on mobile (uses sidebar instead)

---

### BACK-010: Add Estimated Reading Time
**Type:** Feature
**Priority:** P3
**Effort:** Small

**Description:**
Show estimated reading time for each module at the top of the section.

**Acceptance Criteria:**
- [ ] Calculate based on word count
- [ ] Display at section start
- [ ] Format: "X min read"

---

### BACK-011: Add Progress Bar
**Type:** Feature
**Priority:** P3
**Effort:** Small

**Description:**
Add a reading progress bar at the top of the page.

**Acceptance Criteria:**
- [ ] Shows scroll position as percentage
- [ ] Smooth animation
- [ ] Visible but not distracting

---

### BACK-012: Syntax Theme Toggle
**Type:** Feature
**Priority:** P3
**Effort:** Medium

**Description:**
Allow users to choose syntax highlighting theme independent of site theme.

**Acceptance Criteria:**
- [ ] Dropdown in settings or header
- [ ] 2-3 theme options
- [ ] Persisted preference

---

## P4: Future Considerations

### BACK-013: Offline Support (Service Worker)
**Type:** Feature
**Priority:** P4
**Effort:** Large

**Description:**
Add service worker for offline access to documentation.

---

### BACK-014: User Progress Tracking
**Type:** Feature
**Priority:** P4
**Effort:** Large

**Description:**
Track which sections user has read, allow marking as complete.

---

### BACK-015: Real Authentication
**Type:** Feature
**Priority:** P4
**Effort:** X-Large

**Description:**
Replace client-side auth with proper backend authentication.

---

### BACK-016: Interactive Exercises
**Type:** Feature
**Priority:** P4
**Effort:** X-Large

**Description:**
Add interactive coding exercises within the documentation.

---

### BACK-017: Multi-language Support
**Type:** Feature
**Priority:** P4
**Effort:** X-Large

**Description:**
Add support for translating content to other languages.

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
