# Focus Tree Ideological Exclusivity Audit

## Executive summary

- Total focus trees audited: 59
- Trees with healthy ideological exclusivity: 57
- Trees with major ideological bleed issues: 0
- Trees needing minor lock cleanup: 2
- Highest-risk incoherent mixing before fixes: colonial template trees (ALG/AST/CAN/COG/EGY/INS/MAL/NZL/RAJ/SAF) and UKR dual-path tree; each allowed completion of incompatible tracks in one run.
- Biggest AI coherence concerns: AI could chain loyalty + self-rule + workers + anarchist branches in the same game because capstones required all path tracks.

## Country-by-country findings

### ACC (healthy)
- Ideological branch points: no multi-choice ideological split detected by static scan.
- Exclusivity quality: acceptable with current branch gating.

### ACG (healthy)
- Ideological branch points: no multi-choice ideological split detected by static scan.
- Exclusivity quality: acceptable with current branch gating.

### ALB (healthy)
- Ideological branch points: ALB_clan_internal_axis: ALB_clan_civic_line, ALB_clan_security_line, ALB_clan_solidarity_line
- Exclusivity quality: acceptable with current branch gating.

### ALG (healthy)
- Ideological branch points: ALG_colonial_crossroads: ALG_strengthen_the_french_algeria, ALG_organise_the_workers, ALG_raise_the_black_banner
- Exclusivity quality: acceptable with current branch gating.

### ANA (healthy)
- Ideological branch points: no multi-choice ideological split detected by static scan.
- Exclusivity quality: acceptable with current branch gating.

### APF (healthy)
- Ideological branch points: no multi-choice ideological split detected by static scan.
- Exclusivity quality: acceptable with current branch gating.

### ARG (healthy)
- Ideological branch points: no multi-choice ideological split detected by static scan.
- Exclusivity quality: acceptable with current branch gating.

### ASL (healthy)
- Ideological branch points: no multi-choice ideological split detected by static scan.
- Exclusivity quality: acceptable with current branch gating.

### AST (healthy)
- Ideological branch points: AST_colonial_crossroads: AST_strengthen_the_oceanic_dominion, AST_organise_the_workers, AST_raise_the_black_banner
- Exclusivity quality: acceptable with current branch gating.

### AUS (healthy)
- Ideological branch points: AUS_identity_internal_axis: AUS_identity_civic_line, AUS_identity_security_line, AUS_identity_solidarity_line
- Exclusivity quality: acceptable with current branch gating.

### AWU (healthy)
- Ideological branch points: no multi-choice ideological split detected by static scan.
- Exclusivity quality: acceptable with current branch gating.

### BASE_fallback (healthy)
- Ideological branch points: no multi-choice ideological split detected by static scan.
- Exclusivity quality: acceptable with current branch gating.

### BEL (healthy)
- Ideological branch points: BEL_pillar_internal_axis: BEL_pillar_civic_line, BEL_pillar_security_line, BEL_pillar_solidarity_line
- Exclusivity quality: acceptable with current branch gating.

### BRA (healthy)
- Ideological branch points: no multi-choice ideological split detected by static scan.
- Exclusivity quality: acceptable with current branch gating.

### BUL (healthy)
- Ideological branch points: BUL_revanchist_internal_axis: BUL_revanchist_civic_line, BUL_revanchist_security_line, BUL_revanchist_solidarity_line
- Exclusivity quality: acceptable with current branch gating.

### CAN (healthy)
- Ideological branch points: CAN_colonial_crossroads: CAN_strengthen_the_imperial_dominion, CAN_organise_the_workers, CAN_raise_the_black_banner
- Exclusivity quality: acceptable with current branch gating.

### CCW (healthy)
- Ideological branch points: no multi-choice ideological split detected by static scan.
- Exclusivity quality: acceptable with current branch gating.

### CHI (healthy)
- Ideological branch points: no multi-choice ideological split detected by static scan.
- Exclusivity quality: acceptable with current branch gating.

### CHI_warlords (healthy)
- Ideological branch points: no multi-choice ideological split detected by static scan.
- Exclusivity quality: acceptable with current branch gating.

### COG (healthy)
- Ideological branch points: COG_colonial_crossroads: COG_strengthen_the_congo_administration, COG_organise_the_workers, COG_raise_the_black_banner
- Exclusivity quality: acceptable with current branch gating.

### CUB (minor)
- Ideological branch points: CUB_crossroads_of_the_caribbean: CUB_guard_the_republic, CUB_the_open_island
- Bleed-through detected:
  - CUB_guard_the_republic vs CUB_the_open_island under CUB_crossroads_of_the_caribbean lack explicit lock
- Recommended fix type: mutually_exclusive at branch entry + flag-based available gating + bypass on unchosen sibling sub-branches.
- Impact: player clarity and AI coherence.

### CZE (healthy)
- Ideological branch points: CZE_measure_the_fault_lines: CZE_civic_coalition_compacts, CZE_national_solidarity_bloc
- Exclusivity quality: acceptable with current branch gating.

### DEN (healthy)
- Ideological branch points: no multi-choice ideological split detected by static scan.
- Exclusivity quality: acceptable with current branch gating.

### EGY (healthy)
- Ideological branch points: EGY_colonial_crossroads: EGY_strengthen_the_khedival_state, EGY_organise_the_workers, EGY_raise_the_black_banner
- Exclusivity quality: acceptable with current branch gating.

### ENG (healthy)
- Ideological branch points: no multi-choice ideological split detected by static scan.
- Exclusivity quality: acceptable with current branch gating.

### EST (healthy)
- Ideological branch points: EST_consolidation_internal_axis: EST_consolidation_civic_line, EST_consolidation_security_line, EST_consolidation_solidarity_line
- Exclusivity quality: acceptable with current branch gating.

### FIN (healthy)
- Ideological branch points: FIN_cohesion_internal_axis: FIN_cohesion_civic_line, FIN_cohesion_security_line, FIN_cohesion_solidarity_line
- Exclusivity quality: acceptable with current branch gating.

### FRA (healthy)
- Ideological branch points: no multi-choice ideological split detected by static scan.
- Exclusivity quality: acceptable with current branch gating.

### GER (healthy)
- Ideological branch points: GER_the_black_and_red_debate: GER_back_the_party, GER_back_the_communes
- Exclusivity quality: acceptable with current branch gating.

### GRE (healthy)
- Ideological branch points: GRE_legitimacy_internal_axis: GRE_legitimacy_civic_line, GRE_legitimacy_security_line, GRE_legitimacy_solidarity_line
- Exclusivity quality: acceptable with current branch gating.

### HOL (healthy)
- Ideological branch points: HOL_trade_internal_axis: HOL_trade_civic_line, HOL_trade_security_line, HOL_trade_solidarity_line
- Exclusivity quality: acceptable with current branch gating.

### HUN (healthy)
- Ideological branch points: HUN_revision_internal_axis: HUN_revision_civic_line, HUN_revision_security_line, HUN_revision_solidarity_line
- Exclusivity quality: acceptable with current branch gating.

### INS (healthy)
- Ideological branch points: INS_colonial_crossroads: INS_strengthen_the_east_indies_authority, INS_organise_the_workers, INS_raise_the_black_banner
- Exclusivity quality: acceptable with current branch gating.

### IRE (healthy)
- Ideological branch points: IRE_neutrality_debate_internal_axis: IRE_neutrality_debate_civic_line, IRE_neutrality_debate_security_line, IRE_neutrality_debate_solidarity_line
- Exclusivity quality: acceptable with current branch gating.

### ITA (healthy)
- Ideological branch points: ITA_count_the_factions: ITA_regime_conciliation_path, ITA_blackshirt_primacy_path
- Exclusivity quality: acceptable with current branch gating.

### JAP (healthy)
- Ideological branch points: no multi-choice ideological split detected by static scan.
- Exclusivity quality: acceptable with current branch gating.

### LAT (healthy)
- Ideological branch points: LAT_bargaining_internal_axis: LAT_bargaining_civic_line, LAT_bargaining_security_line, LAT_bargaining_solidarity_line
- Exclusivity quality: acceptable with current branch gating.

### LIT (healthy)
- Ideological branch points: LIT_authority_internal_axis: LIT_authority_civic_line, LIT_authority_security_line, LIT_authority_solidarity_line
- Exclusivity quality: acceptable with current branch gating.

### LUX (healthy)
- Ideological branch points: LUX_microstate_internal_axis: LUX_microstate_civic_line, LUX_microstate_security_line, LUX_microstate_solidarity_line
- Exclusivity quality: acceptable with current branch gating.

### MAL (healthy)
- Ideological branch points: MAL_colonial_crossroads: MAL_strengthen_the_straits_dominion, MAL_organise_the_workers, MAL_raise_the_black_banner
- Exclusivity quality: acceptable with current branch gating.

### MEX (healthy)
- Ideological branch points: no multi-choice ideological split detected by static scan.
- Exclusivity quality: acceptable with current branch gating.

### NOR (healthy)
- Ideological branch points: no multi-choice ideological split detected by static scan.
- Exclusivity quality: acceptable with current branch gating.

### NZL (healthy)
- Ideological branch points: NZL_colonial_crossroads: NZL_strengthen_the_pacific_dominion, NZL_organise_the_workers, NZL_raise_the_black_banner
- Exclusivity quality: acceptable with current branch gating.

### POL (healthy)
- Ideological branch points: POL_map_the_encirclement: POL_sanacja_consolidation, POL_parliamentary_compromise, POL_popular_mobilization_bloc
- Exclusivity quality: acceptable with current branch gating.

### POR (healthy)
- Ideological branch points: POR_estate_internal_axis: POR_estate_civic_line, POR_estate_security_line, POR_estate_solidarity_line
- Exclusivity quality: acceptable with current branch gating.

### PRC (healthy)
- Ideological branch points: no multi-choice ideological split detected by static scan.
- Exclusivity quality: acceptable with current branch gating.

### RAJ (healthy)
- Ideological branch points: RAJ_colonial_crossroads: RAJ_strengthen_the_imperial_raj, RAJ_organise_the_workers, RAJ_raise_the_black_banner
- Exclusivity quality: acceptable with current branch gating.

### ROM (healthy)
- Ideological branch points: ROM_court_internal_axis: ROM_court_civic_line, ROM_court_security_line, ROM_court_solidarity_line
- Exclusivity quality: acceptable with current branch gating.

### SAF (healthy)
- Ideological branch points: SAF_colonial_crossroads: SAF_strengthen_the_union_settlement, SAF_organise_the_workers, SAF_raise_the_black_banner
- Exclusivity quality: acceptable with current branch gating.

### SER (healthy)
- Ideological branch points: no multi-choice ideological split detected by static scan.
- Exclusivity quality: acceptable with current branch gating.

### SOV (healthy)
- Ideological branch points: SOV_the_future_of_russia: SOV_army_directorate, SOV_workers_republic, SOV_free_territories, SOV_national_union_state
- Exclusivity quality: acceptable with current branch gating.

### SPA (healthy)
- Ideological branch points: SPA_stabilization_internal_axis: SPA_stabilization_civic_line, SPA_stabilization_security_line, SPA_stabilization_solidarity_line
- Exclusivity quality: acceptable with current branch gating.

### SPR (minor)
- Ideological branch points: SPR_hollow_neutrality: SPR_restore_the_cortes, SPR_integralist_revival, SPR_the_red_hinterland
- Bleed-through detected:
  - SPR_restore_the_cortes vs SPR_the_red_hinterland under SPR_hollow_neutrality lack explicit lock
  - SPR_integralist_revival vs SPR_the_red_hinterland under SPR_hollow_neutrality lack explicit lock
- Recommended fix type: mutually_exclusive at branch entry + flag-based available gating + bypass on unchosen sibling sub-branches.
- Impact: player clarity and AI coherence.

### SWE (healthy)
- Ideological branch points: no multi-choice ideological split detected by static scan.
- Exclusivity quality: acceptable with current branch gating.

### SWI (healthy)
- Ideological branch points: SWI_cantonal_internal_axis: SWI_cantonal_civic_line, SWI_cantonal_security_line, SWI_cantonal_solidarity_line
- Exclusivity quality: acceptable with current branch gating.

### TUR (healthy)
- Ideological branch points: no multi-choice ideological split detected by static scan.
- Exclusivity quality: acceptable with current branch gating.

### UKR (healthy)
- Ideological branch points: UKR_between_empires: UKR_revive_the_free_territory, UKR_seek_the_black_banner
- Exclusivity quality: acceptable with current branch gating.

### USA (healthy)
- Ideological branch points: USA_marches_in_the_streets: USA_union_of_counties, USA_the_red_caucuses; USA_the_union_fractures: USA_market_commonwealth, USA_the_free_counties, USA_the_workers_republic, USA_the_generals_settle_accounts
- Ideological branch locking status: post-fracture regime paths now use explicit mutual exclusion and path flags; sibling second-tier focuses are bypassed when on a rival path.
- Remaining manual note: early unrest split (`USA_union_of_counties` vs `USA_the_red_caucuses`) can be left as shared pre-fracture agitation unless design wants harder pre-break lock.

### YUG (healthy)
- Ideological branch points: YUG_federal_internal_axis: YUG_federal_civic_line, YUG_federal_security_line, YUG_federal_solidarity_line
- Exclusivity quality: acceptable with current branch gating.

## Most serious ideological conflicts

- Colonial-template trees permitted all four ideological lanes to be completed before capstone, creating impossible hybrid states.
- UKR allowed both anarchist and communist revolutionary paths to be completed before national capstone.
- Several trees rely only on popularity shifts without hard branch lock signals, making commitment readability weak.

## Recommended implementation methods

- **mutually_exclusive fixes**: add explicit exclusivity between branch-entry focuses at each ideological pivot.
- **available trigger fixes**: add one-time branch flags and deny rival entry focuses once any path flag is set.
- **country flag / scripted trigger fixes**: set permanent per-path flags in completion_reward for commitment focuses; consider centralizing in scripted triggers in future cleanup pass.
- **event/decision lock fixes**: where event-driven path unlocks exist (e.g., hidden paths), set lock flags in the same events to close rival tree sections.
- **AI pathing fixes**: ensure ai_will_do and strategy plans align with selected branch flags to avoid cross-ideology drift.
- **manual review items**: majors with complex hidden paths (GER/ENG/FRA/USA/SOV/JAP/ITA/CHI) should receive hand-authored lock audits at major commitment nodes.

## Technical notes

- Files changed: common/national_focus/AOTA_ALG.txt, AOTA_AST.txt, AOTA_CAN.txt, AOTA_COG.txt, AOTA_EGY.txt, AOTA_INS.txt, AOTA_MAL.txt, AOTA_NZL.txt, AOTA_RAJ.txt, AOTA_SAF.txt, AOTA_UKR.txt, AOTA_USA.txt.
- Lock flags added: `<TAG>_ideology_path_loyalist`, `<TAG>_ideology_path_self_rule`, `<TAG>_ideology_path_workers`, `<TAG>_ideology_path_anarchist`; and UKR anarchist/communist path flags.
- Focus gating added: mutually_exclusive + available checks on branch entries; bypass on sibling second-tier nodes to preserve capstone progression without branch deletion.
- AI adjustments made: indirect via focus availability/lock logic; no separate ai_strategy files modified in this pass.
- Remaining edge cases: complex hidden/event-driven ideological pivots in several majors still need bespoke manual lock design to match lore intent exactly.