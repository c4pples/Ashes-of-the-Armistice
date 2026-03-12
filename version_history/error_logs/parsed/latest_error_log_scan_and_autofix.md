# HOI4 Error Log Scan + Safe Auto-fix Report

## A. Executive summary
- **Newest log(s) scanned:** `version_history/error_logs/raw/error.log` (modified 2026-03-12 00:41:54).
- **Major issue clusters found:** 10.
- **Safe fixes applied automatically:** 4 clusters fixed.
- **Top remaining blockers:**
  1. Focus-tree effect/scope errors (hundreds of lines across multiple focus files).
  2. AI strategy parser errors in `common/ai_strategy/GER.txt`.
  3. Character parser errors for `portrait_path` in `common/characters/AOTA_v10_characters.txt` and `AOTA_v13_characters.txt`.
  4. Duplicate DB IDs (`OTT` alias and ideology duplicates).
  5. Missing/duplicated sound assets in `sound/*.asset`.

## B. Hard blockers found
1. **State history parser failures caused by BOM tokenization** (`history/states/*.txt`) generated massive parser spam and likely prevented reliable state database ingestion.
2. **Broken interface sprite block structure** in `interface/AOTA_portraits.gfx` (multiple `spriteType` entries parsed outside `spriteTypes = { ... }`).
3. **Opinion modifier files missing root container block** in:
   - `common/opinion_modifiers/AOTA_opinion_modifiers.txt`
   - `common/opinion_modifiers/AOTA_ottoman_opinions.txt`

## C. Major errors found
- `state_file_parse_errors`: 2268
- `focus_effect_scope_errors`: 735
- `audio_missing_or_duplicates`: 506
- `localisation_bom`: 84
- `invalid_state_id`: 40
- `character_portrait_path_parser`: 26
- `ai_strategy_syntax`: 22
- `portraits_gfx_structure`: 16
- `opinion_modifiers_structure`: 12
- `duplicate_db_id`: 6

## D. Safe fixes applied

### 1) Removed parser-breaking BOM bytes from state history files
- **Issue summary:** `history/states/*.txt` produced repeated `Unexpected token` errors involving `﻿` and `=`, typically near line 2.
- **Source files:** all state files with UTF-8 BOM prefix.
- **Change:** removed leading UTF-8 BOM from state script files.
- **Why safe:** HOI4 script files in `history/states` do not require BOM; removing BOM is a technical encoding normalization that preserves gameplay content.
- **Confidence:** **High**.

### 2) Added required UTF-8 BOM to localisation files explicitly flagged by log
- **Issue summary:** `Missing UTF8 BOM` on many `localisation/english/*.yml` files.
- **Source files:** all localisation files listed by `Missing UTF8 BOM` lines in the newest `error.log`.
- **Change:** prepended UTF-8 BOM to each flagged localisation file lacking it.
- **Why safe:** HOI4 localization loader expects BOM on these files; this is encoding-only with no content rewrite.
- **Confidence:** **High**.

### 3) Fixed `interface/AOTA_portraits.gfx` sprite block structure
- **Issue summary:** repeated `Unexpected token: spriteType` from `interface/AOTA_portraits.gfx`.
- **Source file:** `interface/AOTA_portraits.gfx`.
- **Change:** merged loose `spriteType` entries into the existing `spriteTypes = { ... }` block and restored proper closing brace.
- **Why safe:** strictly structural parser repair; no sprite names/paths changed.
- **Confidence:** **High**.

### 4) Wrapped opinion modifiers in required root container
- **Issue summary:** repeated `Unexpected token` for modifier keys in opinion modifier files.
- **Source files:**
  - `common/opinion_modifiers/AOTA_opinion_modifiers.txt`
  - `common/opinion_modifiers/AOTA_ottoman_opinions.txt`
- **Change:** wrapped entries with `opinion_modifiers = { ... }`.
- **Why safe:** standard HOI4 database file structure; keys and values unchanged.
- **Confidence:** **High**.

## E. Issues not auto-fixed
1. **Focus effect/scope errors (735 lines)**
   - **Why not auto-fixed:** multiple plausible intent outcomes (`Invalid scope`, `Unknown effect-type`, cross-file logic implications).
   - **Recommended next step:** validate each affected focus branch by intended scope (`state`, `country`, etc.) and patch with scripted test pass.

2. **Duplicate DB IDs (`common/country_tag_aliases`, `common/ideologies`)**
   - **Why not auto-fixed:** could be intentional override/load-order behavior; blind deletion can break compatibility.
   - **Recommended next step:** resolve by canonical source-of-truth file and remove/rename duplicate definitions deliberately.

3. **AI strategy parse errors in `common/ai_strategy/GER.txt`**
   - **Why not auto-fixed:** requires semantic interpretation of AI plan blocks.
   - **Recommended next step:** inspect around reported lines for malformed nesting or misplaced `state` entries.

4. **Character `portrait_path` parser errors**
   - **Why not auto-fixed:** likely schema mismatch (character format version differences) and may need broader migration strategy.
   - **Recommended next step:** align file schema with current HOI4 character database format.

5. **Audio missing/duplicate assets**
   - **Why not auto-fixed:** unclear whether missing files should be added, redirected, or removed; content-sensitive.
   - **Recommended next step:** audit `sound/ww_vo.asset` and `sound/gui/gtd/gtd_gui.asset` against existing wav/ogg assets.

## F. Likely noise / low-priority warnings
- `incorrect checksum for DLC` (environment/content setup related).
- Repeated sound duplicate registration warnings (often downstream of asset list duplication).

## G. Files changed
- Massive encoding normalization in `history/states/*.txt` (BOM removal).
- Localisation encoding fixes in flagged `localisation/english/*.yml` files.
- Structural parser fixes:
  - `interface/AOTA_portraits.gfx`
  - `common/opinion_modifiers/AOTA_opinion_modifiers.txt`
  - `common/opinion_modifiers/AOTA_ottoman_opinions.txt`

## H. Top priority remaining work
1. Fix focus-tree invalid effect/scope clusters.
2. Repair `common/ai_strategy/GER.txt` parser issues.
3. Resolve duplicate DB IDs (aliases/ideologies) with explicit canonical ownership.
4. Migrate/repair character `portrait_path` entries to current schema.
5. Audit and de-duplicate sound asset declarations and missing file paths.
