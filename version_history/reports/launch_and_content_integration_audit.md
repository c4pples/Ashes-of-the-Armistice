# Launch and Content Integration Audit (AOTA)

## Scope
Launcher/descriptor correctness, script integrity checks, cross-system references (events/focuses/ideas/scripted content), and integration stability.

## Key outcome
- Launch metadata is valid.
- Core parser/reference checks passed.
- One critical focus-ID parse issue in Ireland tree was fixed.
- Main remaining risk is localization-key duplication across versioned files.

## Fixed technical issue
- Normalized malformed Ireland focus IDs and synchronized matching localization keys.
  - `common/national_focus/AOTA_IRE.txt`
  - `localisation/english/AOTA_IRE_focus_l_english.yml`

## Integration findings
- Event calls resolve to defined event IDs in scan.
- Focus prerequisite references resolve in scan.
- Idea references resolve in scan.
- Scripted trigger/effect `AOTA_*` calls resolve in scan.

## Risks still open
1. Duplicate localization keys (high count) across multiple files produce silent overwrite behavior.
2. Version-layered architecture is powerful but prone to accidental content shadowing.

## Recommendations
1. Establish single-owner files per localization key family.
2. Add automated duplicate-key linting to pre-release checks.
3. Run manual chain tests for USA/SOV/ENG high-interaction arcs.
