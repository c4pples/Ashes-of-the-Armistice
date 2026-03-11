# HOI4 Map / Ownership Change Audit (AOTA)

## A. Executive summary
- Total states identified as intentionally overridden vs vanilla baseline (from prior canonical reset report): **51**.
- Owner/controller setup changes vs vanilla (high-confidence): **32**.
- Core/claim setup changes vs vanilla: **Needs manual vanilla file diff for exact count** (workspace lacks bundled vanilla `history/states` source files; this audit used the mod's own canonical override ledger as baseline).
- Suspected technical errors (hard failures found in this pass): **0** (no duplicate state IDs, no duplicated province-to-state assignment, no broken state ID references in scanned map-effect scripts).
- Lore concerns: **0 confirmed blockers**, **3 medium-risk review clusters** (Danubian fringes, Levant/Mesopotamia continuity, East Africa remnant holding).
- Likely intentional changes: **32 confirmed + 19 baseline-preserving overrides**.

## B. State-by-state change log
| State ID | State name/file label | Vanilla owner (baseline) | Mod owner/controller | Mod cores | Mod claims | Owner change? | Likely intent | Lore assessment | Technical risk |
|---:|---|---|---|---|---|---|---|---|---|
| 4 | 4-Austria | AUS | AUS/AUS | AUS,GER | - | No/likely same | Likely baseline/maintenance | Consistent (no meaningful owner divergence from vanilla baseline) | Low |
| 9 | 9-Czechoslovakia | CZE | AUS/AUS | AUS,CZE | - | Yes | Intentional lore divergence | Consistent with surviving Danubian monarchy | Low |
| 28 | 28-Alcase | FRA | GER/? | FRA,GER | - | Yes | Intentional lore divergence | Consistent with German victory/remnant colonial framing | Low |
| 39 | 39-South Tyrol | ITA | AUS/? | AUS,ITA,LBV | AUS | Yes | Intentional lore divergence | Consistent with surviving Danubian monarchy | Low |
| 43 | 43-Hungary | HUN | AUS/? | AUS,HUN | - | Yes | Intentional lore divergence | Consistent with surviving Danubian monarchy | Low |
| 45 | 45-Yugoslavia | YUG | AUS/? | AUS,SER,YUG | - | Yes | Intentional lore divergence | Consistent with surviving Danubian monarchy | Low |
| 69 | 69-Sudatenland | CZE | AUS/AUS | AUS,CZE,GER | - | Yes | Intentional lore divergence | Consistent with surviving Danubian monarchy | Low |
| 70 | 70-Slovakia | CZE | AUS/AUS | AUS,CZE,SLO | - | Yes | Intentional lore divergence | Consistent with surviving Danubian monarchy | Low |
| 71 | 71-East Slovakia | CZE | AUS/AUS | AUS,CZE,SLO | - | Yes | Intentional lore divergence | Consistent with surviving Danubian monarchy | Low |
| 73 | 73-Carpathian Ruthenia | CZE | AUS/AUS | AUS,CZE,HUN,SLO,UKR | HUN | Yes | Intentional lore divergence | Consistent with surviving Danubian monarchy | Low |
| 74 | 74-East Sudatenland | CZE | AUS/AUS | AUS,CZE,GER | - | Yes | Intentional lore divergence | Consistent with surviving Danubian monarchy | Low |
| 75 | 75-Moravia | CZE | AUS/AUS | AUS,CZE | - | Yes | Intentional lore divergence | Consistent with surviving Danubian monarchy | Low |
| 76 | 76-Northern Transylvania | ROM | AUS/? | AUS,ROM,TRA | - | Yes | Intentional lore divergence | Consistent with surviving Danubian monarchy | Low |
| 80 | 80-Bocovina | ROM | AUS/? | AUS,ROM,UKR | - | Yes | Intentional lore divergence | Consistent with surviving Danubian monarchy | Low |
| 82 | 82-Banat | ROM | AUS/? | AUS,ROM,TRA | - | Yes | Intentional lore divergence | Consistent with surviving Danubian monarchy | Low |
| 83 | 83-crisana | ROM | AUS/? | AUS,ROM,TRA | - | Yes | Intentional lore divergence | Consistent with surviving Danubian monarchy | Low |
| 84 | 84-Transylvania | ROM | AUS/? | AUS,ROM,TRA | - | Yes | Intentional lore divergence | Consistent with surviving Danubian monarchy | Low |
| 86 | 86-Poznan | POL | GER/? | GER,POL | GER,PRE | Yes | Intentional lore divergence | Consistent with German victory/remnant colonial framing | Low |
| 91 | 91-Tarnopol | POL | AUS/? | AUS,POL,UKR | - | Yes | Intentional lore divergence | Consistent with surviving Danubian monarchy | Low |
| 102 | 102-North-Eastern Slovenia | YUG | AUS/? | AUS,SLV,YUG | - | Yes | Intentional lore divergence | Consistent with surviving Danubian monarchy | Low |
| 103 | 103-Croatia | YUG | AUS/? | AUS,CRO,YUG | ITA | Yes | Intentional lore divergence | Consistent with surviving Danubian monarchy | Low |
| 104 | 104-Bosnia | YUG | AUS/? | AUS,BOS,YUG | - | Yes | Intentional lore divergence | Consistent with surviving Danubian monarchy | Low |
| 109 | 109-Eastern Croatia | YUG | AUS/? | AUS,CRO,YUG | - | Yes | Intentional lore divergence | Consistent with surviving Danubian monarchy | Low |
| 152 | 152-Upper Austria | AUS | AUS/AUS | AUS,GER | - | No/likely same | Likely baseline/maintenance | Consistent (no meaningful owner divergence from vanilla baseline) | Low |
| 153 | 153-Tyrol | AUS | AUS/AUS | AUS,GER | - | No/likely same | Likely baseline/maintenance | Consistent (no meaningful owner divergence from vanilla baseline) | Low |
| 154 | 154-Southern plain | HUN | AUS/? | AUS,HUN | - | Yes | Intentional lore divergence | Consistent with surviving Danubian monarchy | Low |
| 291 | 291-Iraq | IRQ | TUR/? | IRQ,TUR | KUR | Yes | Intentional lore divergence | Consistent with stronger Ottoman sphere in Levant/Mesopotamia | Low |
| 423 | 423-Madras | RAJ | RAJ/? | RAJ | - | No/likely same | Likely baseline/maintenance | Consistent (no meaningful owner divergence from vanilla baseline) | Low |
| 424 | 424-Andra Pradesh | RAJ | RAJ/? | RAJ | - | No/likely same | Likely baseline/maintenance | Consistent (no meaningful owner divergence from vanilla baseline) | Low |
| 425 | 425-Mysore | RAJ | RAJ/? | MYS,RAJ | - | No/likely same | Likely baseline/maintenance | Consistent (no meaningful owner divergence from vanilla baseline) | Low |
| 426 | 426-Orissa | RAJ | RAJ/? | RAJ | - | No/likely same | Likely baseline/maintenance | Consistent (no meaningful owner divergence from vanilla baseline) | Low |
| 427 | 427-Hyderabad | RAJ | RAJ/? | HYD,RAJ | - | No/likely same | Likely baseline/maintenance | Consistent (no meaningful owner divergence from vanilla baseline) | Low |
| 428 | 428-Western Indian States | RAJ | RAJ/? | RAJ,WIS | - | No/likely same | Likely baseline/maintenance | Consistent (no meaningful owner divergence from vanilla baseline) | Low |
| 429 | 429-Bombay | RAJ | RAJ/? | RAJ | KHL | No/likely same | Likely baseline/maintenance | Consistent (no meaningful owner divergence from vanilla baseline) | Low |
| 430 | 430-Bangladesh | RAJ | RAJ/? | BAN,PAK,RAJ | - | No/likely same | Likely baseline/maintenance | Consistent (no meaningful owner divergence from vanilla baseline) | Low |
| 431 | 431-Calcutta | RAJ | RAJ/? | RAJ | - | No/likely same | Likely baseline/maintenance | Consistent (no meaningful owner divergence from vanilla baseline) | Low |
| 432 | 432-Assam | RAJ | RAJ/? | RAJ | - | No/likely same | Likely baseline/maintenance | Consistent (no meaningful owner divergence from vanilla baseline) | Low |
| 434 | 434-Arunachal Pradesh | RAJ | RAJ/? | RAJ,TIB | - | No/likely same | Likely baseline/maintenance | Consistent (no meaningful owner divergence from vanilla baseline) | Low |
| 435 | 435-Bihar | RAJ | RAJ/? | RAJ | - | No/likely same | Likely baseline/maintenance | Consistent (no meaningful owner divergence from vanilla baseline) | Low |
| 436 | 436-Central Provinces | RAJ | RAJ/? | RAJ | - | No/likely same | Likely baseline/maintenance | Consistent (no meaningful owner divergence from vanilla baseline) | Low |
| 437 | 437-Central Indian Provinces | RAJ | RAJ/? | CIP,RAJ | - | No/likely same | Likely baseline/maintenance | Consistent (no meaningful owner divergence from vanilla baseline) | Low |
| 438 | 438-United Provinces | RAJ | RAJ/? | RAJ | KHL | No/likely same | Likely baseline/maintenance | Consistent (no meaningful owner divergence from vanilla baseline) | Low |
| 439 | 439-Delhi | RAJ | RAJ/? | RAJ | - | No/likely same | Likely baseline/maintenance | Consistent (no meaningful owner divergence from vanilla baseline) | Low |
| 454 | 454-Israel | ENG | TUR/? | ISR,PAL,TUR | - | Yes | Intentional lore divergence | Consistent with stronger Ottoman sphere in Levant/Mesopotamia | Low |
| 455 | 455-Jordan | ENG | TUR/? | JOR,TUR | - | Yes | Intentional lore divergence | Consistent with stronger Ottoman sphere in Levant/Mesopotamia | Low |
| 546 | 546-Tanganyika | ENG | GER/? | TZN | - | Yes | Intentional lore divergence | Consistent with German victory/remnant colonial framing | Low |
| 553 | 553-Lebanon | FRA | TUR/? | LEB,TUR | - | Yes | Intentional lore divergence | Consistent with stronger Ottoman sphere in Levant/Mesopotamia | Low |
| 554 | 554-Syria | FRA | TUR/? | SYR,TUR | - | Yes | Intentional lore divergence | Consistent with stronger Ottoman sphere in Levant/Mesopotamia | Low |
| 676 | 676-Mosul | IRQ | TUR/? | ASY,IRQ,KUR,TUR | - | Yes | Intentional lore divergence | Consistent with stronger Ottoman sphere in Levant/Mesopotamia | Low |
| 677 | 677-Aleppo | FRA | TUR/? | SYR,TUR | - | Yes | Intentional lore divergence | Consistent with stronger Ottoman sphere in Levant/Mesopotamia | Low |
| 680 | 680-Deir-az-Zur | FRA | TUR/? | KUR,SYR,TUR | - | Yes | Intentional lore divergence | Consistent with stronger Ottoman sphere in Levant/Mesopotamia | Low |

Notes:
- "Vanilla owner" values were reconstructed from vanilla 1936 geopolitical defaults and the mod's own v35 canonical override record.
- For a fully mechanical line-by-line core/claim diff against vanilla, import exact vanilla `history/states` files for the target game version and rerun this audit script.

## C. Province/state definition concerns
- Duplicate state IDs: **0**.
- States missing province blocks: **0**.
- Provinces assigned to multiple states: **0**.
- No obvious province crosswalk corruption was detected from state-history text structure alone.
- Limitation: province-ID existence could not be validated absolutely because `map/definition.csv` is not included in this mod workspace.

## D. Technical parse issues
- Map-effect command scan completed for `events/` and `common/` (`transfer_state`, `set_owner`, `set_controller`, `add_core_of`, `add_claim_by`, etc.).
- Broken state references found in scanned scripts: **0**.
- High-volume vanilla tags are referenced in state cores/claims; these are expected to resolve via base-game tag definitions at runtime.
- Notable script-level risk: duplicated US-fracture transfer blocks in `events/AOTA_events.txt` should be kept synchronized to avoid divergent post-event ownership outcomes.

## E. Lore review
### Changes that fit lore well
- Danubian restoration cluster (Czech/Hungarian/Transylvanian/Balkan states to `AUS`) is internally coherent with the mod's surviving Habsburg setup.
- German retention of Alsace/Poznan and Tanganyika matches the stated "partial colonial survivor" framing.
- Ottoman hold over Levant + Mesopotamia (including Syria/Lebanon and Iraq frontier states) matches the mod's timeline premise.

### Questionable or needs-manual-review items
- `546-Tanganyika` under `GER`: lore-consistent but strategically high-impact; verify diplomatic/event scaffolding prevents immersion-breaking peacetime AI behavior.
- `677-Aleppo` and `680-Deir-az-Zur` under `TUR`: ensure adjacent Arab cores/claims and revolt scripting align with intended Ottoman administrative model.
- Border continuity in Danubian fringe states (`91`, `102`, `109`) should be checked in-game for resistance/compliance pressure and faction diplomacy coherence.

## F. Recommended fixes
### Safe technical fixes
- Add a maintained machine-readable baseline manifest (state -> vanilla owner/controller/cores hash) to future-proof audits.
- Add a CI lint step that validates map-effect state IDs/tags against a merged tag set (mod + vanilla export).
- Consolidate duplicate US-partition ownership effects into a single scripted effect to reduce drift risk.

### Likely lore fixes
- No immediate lore-breaking ownership errors were confirmed.
- Optional: add flavor/event text hooks explaining German East African continuity and Ottoman Levant governance to reinforce plausibility.

### Manual review required
- Run one follow-up audit with exact vanilla files for the same HOI4 patch level to produce a strict core/claim delta count.
- In-game observe first 30 days for enclave/exclave logistics in Danubian and Ottoman border regions.

## Appendix: map-effect references detected (ownership/core-affecting)
- `events/AOTA_events.txt:50` -> `add_claim_by` on state `39`
- `events/AOTA_events.txt:173` -> `add_core_of` on state `395`
- `events/AOTA_events.txt:174` -> `add_core_of` on state `394`
- `events/AOTA_events.txt:175` -> `add_core_of` on state `393`
- `events/AOTA_events.txt:176` -> `add_core_of` on state `396`
- `events/AOTA_events.txt:177` -> `add_core_of` on state `261`
- `events/AOTA_events.txt:178` -> `add_core_of` on state `375`
- `events/AOTA_events.txt:179` -> `add_core_of` on state `374`
- `events/AOTA_events.txt:180` -> `add_core_of` on state `372`
- `events/AOTA_events.txt:181` -> `add_core_of` on state `367`
- `events/AOTA_events.txt:182` -> `add_core_of` on state `368`
- `events/AOTA_events.txt:183` -> `add_core_of` on state `378`
- `events/AOTA_events.txt:184` -> `add_core_of` on state `829`
- `events/AOTA_events.txt:185` -> `add_core_of` on state `385`
- `events/AOTA_events.txt:186` -> `add_core_of` on state `386`
- `events/AOTA_events.txt:187` -> `add_core_of` on state `379`
- `events/AOTA_events.txt:188` -> `add_core_of` on state `358`
- `events/AOTA_events.txt:189` -> `add_core_of` on state `359`
- `events/AOTA_events.txt:190` -> `add_core_of` on state `360`
- `events/AOTA_events.txt:191` -> `add_core_of` on state `932`
- `events/AOTA_events.txt:192` -> `add_core_of` on state `150`
- `events/AOTA_events.txt:193` -> `add_core_of` on state `364`
- `events/AOTA_events.txt:194` -> `add_core_of` on state `365`
- `events/AOTA_events.txt:195` -> `add_core_of` on state `366`
- `events/AOTA_events.txt:196` -> `add_core_of` on state `362`
- `events/AOTA_events.txt:197` -> `add_core_of` on state `363`
- `events/AOTA_events.txt:198` -> `add_core_of` on state `369`
- `events/AOTA_events.txt:199` -> `add_core_of` on state `361`
- `events/AOTA_events.txt:233` -> `add_core_of` on state `395`
- `events/AOTA_events.txt:234` -> `add_core_of` on state `394`
- `events/AOTA_events.txt:235` -> `add_core_of` on state `393`
- `events/AOTA_events.txt:236` -> `add_core_of` on state `396`
- `events/AOTA_events.txt:237` -> `add_core_of` on state `261`
- `events/AOTA_events.txt:238` -> `add_core_of` on state `375`
- `events/AOTA_events.txt:239` -> `add_core_of` on state `374`
- `events/AOTA_events.txt:240` -> `add_core_of` on state `372`
- `events/AOTA_events.txt:241` -> `add_core_of` on state `364`
- `events/AOTA_events.txt:242` -> `add_core_of` on state `365`
- `events/AOTA_events.txt:243` -> `add_core_of` on state `366`
- `events/AOTA_events.txt:244` -> `add_core_of` on state `367`
- `events/AOTA_events.txt:245` -> `add_core_of` on state `368`
- `events/AOTA_events.txt:246` -> `add_core_of` on state `369`
- `events/AOTA_events.txt:247` -> `add_core_of` on state `378`
- `events/AOTA_events.txt:248` -> `add_core_of` on state `829`
- `events/AOTA_events.txt:249` -> `add_core_of` on state `385`
- `events/AOTA_events.txt:250` -> `add_core_of` on state `386`
- `events/AOTA_events.txt:251` -> `add_core_of` on state `379`
