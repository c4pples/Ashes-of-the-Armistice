# AOTA Deep System Audit (Launch, Script, Integration, Pacing, Prose)

## A. Executive summary

- **Launcher readiness:** Good. `descriptor.mod` and `AOTA.mod` are present, coherent, and include matching `name`, `version`, and `supported_version`; `AOTA.mod` includes `path="mod/AOTA"` as expected for launcher pickup.
- **Parse health:** Mostly healthy after one critical fix (Ireland focus IDs). Braces are balanced across scanned script/config files.
- **Event/focus integrity:** Core references (event IDs, focus prerequisites, idea references) are internally consistent in automated checks. Main structural weakness is heavy localization key duplication and layered legacy files that can silently overwrite each other.
- **Pacing assessment:** Strong macro scaffolding (major intro + escalation layers), but some systems are content-dense while others are still scaffold-like. Several chains rely on MTTH + broad triggers and should be manually playtested for event pressure.
- **Prose assessment:** Tone is generally coherent with the mod identity (post-armistice strain, ideological fragmentation), but duplicate localization key ownership risks unpredictable prose swaps depending on load order.

### Biggest risks
1. **(Fixed in this pass)** Invalid Ireland focus IDs due embedded spaces causing focus parsing/reference failures.
2. **High volume duplicate localization keys** creating non-deterministic text ownership and prose drift.
3. **Wide multi-version layering** (`v06..v33`) increases accidental override risk across events/focus/prose.

### Highest-priority fixes
1. Keep the Ireland focus key fix (implemented now).
2. Consolidate duplicate localization keys by domain owner file (manual curation).
3. Add a smoke-test playbook for early-game event pressure and split-state chains.

---

## B. Launch blockers

### Confirmed status
- No hard launch blockers found in descriptor files:
  - `descriptor.mod` has valid core metadata and `replace_path` usage.
  - `AOTA.mod` has valid metadata + mod path.
- No UTF-8 decoding failures in text/script/localization scan set.

### Potential launcher/load warnings (non-blocking)
- `replace_path = "history/states"` is intentional but high-impact; any missing/partial state definitions in mod scope fully replace vanilla state directory behavior and should be maintained carefully.

---

## C. Hard parse/script issues

### Fixed in this audit

1. **Critical (fixed): malformed focus IDs in Ireland tree**
   - **File:** `common/national_focus/AOTA_IRE.txt`
   - **Issue:** Focus IDs were written as `id = IRE_neutrality debate_*` (space inside ID declaration), which breaks parser expectations and downstream prerequisite/availability references.
   - **Fix applied:** Normalized all to `IRE_neutrality_debate_*`.
   - **Linked fix:** Updated matching localization keys accordingly in `localisation/english/AOTA_IRE_focus_l_english.yml`.
   - **Impact removed:** Focus tree integrity failure, missing loc resolution, and likely error.log spam for invalid focus references.

### Remaining hard-script concerns
- No additional hard parser failures were detected by automated brace/reference scans.

---

## D. Event/focus/decision integration issues

### Major warnings
1. **Localization ownership collisions (high risk to player-facing coherence)**
   - Hundreds of duplicate loc keys exist across versioned/localized files (e.g. SOV event prose keys and ENG party/event keys duplicated across multiple files).
   - Likely runtime behavior: last-loaded file wins, causing silent prose/tone swaps.
   - **Classification:** Major (polish + narrative consistency risk, not parser crash).

2. **Legacy layering complexity**
   - The mod uses many version-sliced files (`AOTA_vXX_*`) plus country-specific packs.
   - This architecture is flexible but increases accidental override risk for events, focuses, and loc keys.
   - **Classification:** Warning (maintenance risk).

### Integration checks that passed
- Event call references (`country_event/news_event id = ...`) resolved to defined event IDs in scan.
- Focus prerequisite references resolved to existing focus IDs in scan.
- Idea add/remove/has references resolved to defined ideas in scan.
- Scripted trigger/effect invocations with `AOTA_* = yes` resolved in scan.

---

## E. Pacing review by country/system

## Fast / potentially noisy
- **US fracture + splinter aftermath layer** (`aota.200+` chain) can create heavy world-state churn quickly; chain is content-rich and should be tested for player overwhelm if combined with early global escalation triggers.

## Slow / underconnected
- Systems marked as scaffolds (multiple `*_scaffold.txt` content files, v0.15 scaffold notes) indicate some domains are intentionally reserved but currently thin.

## Good cadence areas
- Major intro event framing (`v30/v31`) provides strong narrative anchoring before heavier escalation systems.

## Manual pacing checks recommended
1. GER/FRA/ENG first 180 days for event pressure vs focus tempo.
2. USA collapse branches for stabilization windows after split.
3. SOV reunification pressures to ensure momentum without instant over-escalation.

---

## F. Prose review by severity

### Critical immersion breakers
- None found as outright broken text formatting after the Ireland key fix.

### Clarity / consistency issues
- Duplicate key ownership means prose variants can be loaded unexpectedly (same key, different sentence tone).

### Tonal consistency
- Core narrative voice is cohesive (strained postwar legitimacy, ideological fragmentation), but duplicated keys can inject tonal mismatches if overwritten by older/alternate prose packs.

### Minor polish suggestions
- Continue reducing placeholder terminology in player-facing areas where possible.
- Ensure each event’s title/desc lives in a single authoritative file.

---

## G. Lore consistency review

### Where implementation and lore conflict
- No direct lore contradiction was hard-confirmed in script logic checks.
- However, duplicate loc key ownership can cause lore voice drift between variants.

### Where content works especially well
- Intro framing + major crisis super-event structure aligns well with the mod’s divergent-history identity.
- Country-specific divergence (US splinters, SOV reunification pressures, ENG overhaul) is mechanically supported.

---

## H. Recommended fixes

### Safe technical fixes
1. ✅ Keep the Ireland focus ID normalization and matching loc-key normalization (done).
2. Add CI-style lint scripts for:
   - duplicate localization key detection,
   - malformed focus ID token detection,
   - unresolved event/focus/idea references.

### Safe content-linking fixes
1. Assign authoritative owner files for event prose key families (`aota_1000_*`, `AOTA_SOV_22xx_*`, `aota_eng_100x_*`) and remove duplicates.

### Pacing improvements
1. Add lightweight cooldown/guardrails where early event MTTH stacks with major split/escalation arcs.
2. Stage some geopolitical reactions behind additional world-state gates to reduce same-week narrative pileups.

### Prose polish
1. Consolidate duplicated keys to single-source voice for each arc.
2. Keep country voice distinct but lexically consistent within each arc owner file.

### Manual review required
1. Full-country playthrough sweeps: GER, FRA, ENG, USA, SOV, TUR.
2. AI-only observer pass to day ~900 for event spam and stalled branches.

---

## I. Final readiness assessment

- **Safe to launch?** Yes.
- **Safe to test?** Yes, and improved versus pre-fix state.
- **Likely to produce error.log spam?** Reduced by Ireland focus fix; still likely some warning-level noise from localization duplication/overrides.
- **Likely to create broken country paths?** No obvious hard breaks in automated reference checks; manual pacing/path QA still required for complex chains.

### Top manual playtest priorities
1. Ireland focus progression (confirm all branches visible/completable with correct loc).
2. USA fracture chain continuity and post-fracture agency pacing.
3. ENG/SOV event prose consistency across file load order.
