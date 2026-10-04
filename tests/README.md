# Cross-Component Verification

Status: placeholder; no executable application test suite exists yet.

Keep backend unit tests beside the backend; this folder is for integration and
end-to-end checks crossing API, MCP, and UI boundaries.

Planned checks:
- Contract validity and source ID/URL/date preservation across components.
- Fixture-driven digest browsing, source links, and honest error/stale states.
- Desktop/mobile layout, keyboard navigation, and no horizontal overflow.
- Model/source failure drills with deterministic automated stubs.

Live-source and real local-model smoke checks are separate from deterministic CI gates.
Only add CI once real local commands pass; do not add a workflow that pretends to test
placeholder folders. Record actual results using the
[evidence template](../docs/evidence/verification-template.md).