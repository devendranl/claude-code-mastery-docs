# Pending Decisions

Decisions requiring human input are documented here.
Format: Context, Options, Recommendation, Status

---

## Pending

*No pending decisions at this time.*

---

## Approved

### DEC-001: Single-File Architecture
**Date:** 2026-02-01 (Retrofit)
**Context:** Project uses single index.html file containing all HTML, CSS, and JavaScript.
**Decision:** Maintain single-file architecture for simplicity.
**Rationale:**
- No build step required
- Easy deployment to Vercel
- Suitable for documentation site scope
- Fast initial load (single request)

**Status:** Approved (existing pattern)

---

### DEC-002: Client-Side Authentication
**Date:** 2026-02-01 (Retrofit)
**Context:** Site uses hardcoded test credentials stored in JavaScript.
**Decision:** Keep simple auth for gated content access.
**Rationale:**
- Sufficient for limiting access to course content
- No backend required
- Easy to update credentials
- NOT suitable for sensitive data protection

**Status:** Approved (existing pattern)

**Note:** If real user authentication is needed in the future, this will require a backend service and proper security review.

---

### DEC-003: CDN Dependencies
**Date:** 2026-02-01 (Retrofit)
**Context:** Highlight.js and Fuse.js loaded from CDN.
**Decision:** Continue using CDN for external libraries.
**Rationale:**
- No build step needed
- Good caching from CDN
- Reduces repo size
- Easy to update versions

**Status:** Approved (existing pattern)
