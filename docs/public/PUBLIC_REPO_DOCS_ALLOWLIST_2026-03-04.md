# Public Repo Docs Allowlist (2026-03-04)

## Objective

Define what can be published now to the public repository, and what should remain internal.

## Safe To Publish Now

1. `docs/public/AEI_INVESTOR_ONE_PAGER_PUBLIC_2026-03-04.md`
2. `docs/public/AEI_PRODUCT_SPECIFICATION_PUBLIC_2026-03-04.md`
3. `docs/public/AEI_TECHNICAL_ARCHITECTURE_PUBLIC_2026-03-04.md`
4. `docs/public/AEI_HUMAN_COCKPIT_MVP_DESIGN_PUBLIC_2026-03-04.md`
5. `docs/public/AEI_BUSINESS_VALUE_HUMAN_COCKPIT_BRIEF_PUBLIC_2026-03-04.md`
6. `docs/public/PUBLIC_DOCS_INDEX_2026-03-04.md`

## Publish With Redaction First

1. `docs/AEI_INVESTOR_ONE_PAGER_2026-03-04.md`
   - Remove dated internal references and operationally sensitive details.
2. `docs/AEI_HUMAN_COCKPIT_INTERNAL_RFC_2026-03-04.md`
   - Rename as external spec and remove internal decision language.
3. `docs/AEI_MVP_IMPLEMENTATION_ROADMAP_2026-03-04.md`
   - Remove internal sequencing details if publishing externally.

## Keep Internal (Do Not Publish)

1. `docs/FORWARD_TASK_LIST_*.md`
2. `docs/internal/*`
3. `docs/proof/*`
4. `docs/*_PACKET_*`
5. `docs/*_RUNBOOK_*` that include operational recovery details
6. Any file containing:
   - internal hostnames, ports, tunnel commands, workflow internals, artifact paths, or enforcement bypass logic

## Public Repo Baseline Recommendation

1. Start with a minimal public docs set:
   - public investor one-pager
   - public product specification
   - public technical architecture
   - public cockpit MVP design
   - public business value brief
2. Add an explicit “public docs only” index in the public repo root.
3. Keep all governance evidence packets and operational controls private.
