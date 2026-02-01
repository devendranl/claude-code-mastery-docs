# Current Blockers

Issues preventing progress or requiring attention.

---

## Active Blockers

*No active blockers at this time.*

---

## Potential Improvements (Not Blocking)

### IMP-001: No Automated Testing
**Severity:** Low
**Description:** No automated tests exist for the application.
**Impact:** Changes require manual testing.
**Suggested Action:** Consider adding Playwright E2E tests for critical flows.

### IMP-002: Hardcoded Test Credentials
**Severity:** Low
**Description:** Auth credentials are hardcoded in JavaScript.
**Impact:** Anyone can view source to find credentials.
**Suggested Action:** Acceptable for current use case; document in README that this is intentional.

### IMP-003: No Offline Support
**Severity:** Low
**Description:** Site requires internet for CDN resources.
**Impact:** Won't work offline.
**Suggested Action:** Could add service worker if offline access is needed.

---

## Resolved Blockers

*No resolved blockers yet.*
