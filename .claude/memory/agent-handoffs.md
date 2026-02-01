# Agent Handoffs

Track coordination and handoffs between specialized agents.

---

## Recent Handoffs

### 2026-02-01 - Retrofit Initialization
**From:** Technical Architect
**To:** All Agents
**Context:** Master retrofit establishing Claude-native development environment
**Artifacts Created:**
- .claude/ directory structure
- Agent definitions
- Memory files
- Product documentation

**Next Actions:**
- Each agent should read their definition in `.claude/agents/`
- Review `docs/BACKLOG.md` for relevant work items

---

## Handoff Protocol

When handing off work between agents:

1. **Document the handoff** in this file
2. **Include context:** What was done, what's remaining
3. **List artifacts:** Files created or modified
4. **Specify next actions:** Clear instructions for receiving agent
5. **Update session-log.md:** Note the transition

### Handoff Template
```markdown
### [Date] - [Brief Description]
**From:** [Agent Name]
**To:** [Agent Name]
**Context:** [What was being worked on]
**Artifacts:** [List of files]
**Next Actions:** [What needs to happen next]
```

---

## Agent Communication Guidelines

### Shared Resources
All agents should monitor:
- `.claude/memory/decisions.md` - Pending decisions
- `.claude/memory/blockers.md` - Current issues
- `docs/BACKLOG.md` - Prioritized work

### Conflict Resolution
If two agents need to modify the same file:
1. First agent documents intended changes in `session-log.md`
2. Second agent reviews and coordinates
3. Changes are made sequentially, not in parallel
4. Both agents verify final result
