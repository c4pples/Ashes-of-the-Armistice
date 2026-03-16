# CLAUDE.md

## Project
Ashes of the Armistice (AOTA) is a large-scale Hearts of Iron IV overhaul mod. This repository is the live mod workspace and should be treated as production content, not a scratchpad.

The goal is to improve AOTA’s technical quality, parser reliability, launch reliability, structural consistency, AI usability, and content integration while preserving the mod’s identity, lore, tone, and ambition.

---

## Core Priorities

When working in AOTA, prioritize in this order unless the task explicitly says otherwise:

1. Launcher and descriptor correctness
2. Parser and syntax correctness
3. Broken references and missing links
4. Focus / event / decision / idea / character integration
5. Ideological exclusivity and branch discipline
6. AI usability and pathing coherence
7. State ownership / country setup consistency
8. Maintainability and structure
9. Flavor and content polish
10. Optional cleanup

Do not jump to polish while hard technical failures remain unresolved.

---

## Non-Removal Rule

Do NOT remove existing content wholesale.

That means:
- do not delete entire branches
- do not gut focus trees
- do not erase country content because it is messy
- do not simplify the mod by pruning paths
- do not remove systems just to reduce errors
- do not “solve” complexity by deleting ambition

Preferred approach:
- repair
- gate properly
- restructure safely
- add missing support
- fix references
- clean syntax
- improve maintainability
- preserve intended content

If something is broken, fix it with the smallest effective repair that preserves the content concept.

---

## Lore Preservation Rule

AOTA’s lore, tone, and world structure must be preserved.

Do NOT:
- flatten AOTA into vanilla
- flatten AOTA into Kaiserreich
- import another mod’s lore directly
- overwrite the mod’s unique geopolitical structure
- make sweeping map or ideological changes unless clearly required and supported

Do:
- preserve country identity
- preserve regional logic
- preserve intended alt-history divergence
- preserve content breadth
- preserve the mod’s serious tone

If a fix touches lore-sensitive areas, be conservative and document ambiguity clearly.

---

## Kaiserreich Benchmark Rule

Kaiserreich may be used as a benchmark for:
- scripting discipline
- file structure
- reference hygiene
- gating logic
- AI support patterns
- maintainability
- large-mod professionalism

Kaiserreich must NOT be used as:
- content to copy
- lore to import
- balance to mirror automatically
- country design to clone

Use Kaiserreich as a standards benchmark, not as a template.

---

## Error Log Handling

AOTA uses error logs as a primary debugging source.

### Source folders
- Raw logs: `version_history/error_logs/raw/`
- Parsed reports: `version_history/error_logs/parsed/`
- Archived logs: `version_history/error_logs/archive/`

### Log policy
- Use the newest raw AOTA log as the source of truth for current failures
- Use older AOTA raw and parsed logs as historical context only
- Use older logs to identify recurring issue clusters, chronic bad references, and unstable systems
- Deduplicate repeated spam and identify root causes

When asked to fix from logs:
- do not stop at summarizing
- fix safe, clear issues directly
- preserve lore and content direction
- avoid reckless fixes in ambiguous cases

---

## Reports and Documentation

All generated reports must go in:

- `version_history/reports/`

Do not scatter reports through gameplay folders.

Use clear filenames such as:
- `final_mod_push_review.md`
- `ai_strategy_and_longrun_campaign_audit.md`
- `focus_tree_ideological_exclusivity_audit.md`
- `latest_raw_error_log_fix_pass.md`

When making reports:
- be specific
- separate hard blockers from warnings
- distinguish resolved vs unresolved issues
- identify files and systems affected
- explain why changes were made

---

## Preferred Working Style

When given a task, follow this workflow unless the request is explicitly different:

1. Read the relevant files
2. Read the newest relevant raw AOTA error logs if applicable
3. Identify root causes, not just symptoms
4. Make a structured plan if the task is broad
5. Fix high-impact, low-risk issues first
6. Re-check touched files and references
7. Write a report if the task calls for one
8. Leave clear notes for unresolved ambiguous issues

Do not make broad blind edits without checking surrounding context.

---

## Safe to Fix Automatically

Generally safe, low-risk fixes include:
- malformed syntax
- bad braces
- broken paths
- invalid descriptor setup
- obvious typos in references
- missing namespace declarations where intent is obvious
- broken localisation links where the intended key is obvious
- invalid event / focus / decision references caused by clear naming mistakes
- dead asset references that can be safely removed or redirected
- duplicated scripting mistakes
- broken available / bypass / mutually_exclusive logic when the intended branch structure is obvious
- formatting normalization when logic can be preserved exactly
- one-line file normalization
- obvious parser-risk anti-pattern cleanup
- obvious duplicate owner/controller lines when intended setup is clear

---

## High-Risk Areas: Be Conservative

Do not make aggressive changes without strong evidence in these areas:
- lore-sensitive border changes
- major state ownership disputes
- faction architecture redesign
- large ideological rewrites
- OOB rebalance without clear basis
- major diplomacy overhauls
- country identity renaming without lore support
- anything with multiple plausible intended outcomes

In these cases:
- make the smallest safe improvement
- report ambiguity clearly
- do not guess recklessly

---

## Focus Trees and Ideology

AOTA should follow strong HOI4 branch discipline.

Rules:
- early shared political setup is acceptable
- deep ideological branches should be exclusive
- once a country commits to an ideology, incompatible branches should close
- use `mutually_exclusive`, `available`, `bypass`, country flags, scripted triggers, and event locks as appropriate
- avoid ideological bleed unless explicitly intended
- do not leave deep regime-defining branches broadly cross-accessible

When fixing trees:
- preserve content
- improve discipline
- do not delete branches

---

## AI Rules

AI must be treated as a first-class user of the mod.

When touching systems, consider:
- can AI reach the path?
- can AI use the decisions?
- can AI maintain economy and army growth?
- can AI survive the system’s constraints?
- does AI need weights, flags, or path locks?

Do not assume “player can use it” means the system is complete.

Prefer:
- coherent AI paths
- sensible branch commitment
- limited AI chaos
- usable decisions
- proper `ai_will_do` and `ai_chance`
- stable military and industrial growth

Do not solve AI issues by deleting content.

---

## National Spirits

AOTA should avoid spirit bloat.

When reviewing spirits:
- preserve concepts
- merge redundant spirits where needed
- use evolving spirits when appropriate
- use timed/transitional spirits instead of permanent clutter
- avoid excessive stacking
- preserve country identity while improving readability and balance

Do not delete spirit concepts casually.

---

## Country Presence and Support

Countries present at game start should be intentional.

If a country exists at start but lacks meaningful content:
- determine whether it should remain independent with minimum viable content
- become a constrained background state
- become a subordinate entity
- or be integrated into a stronger lore-consistent structure

Do not leave half-supported noise tags untouched if they distort flow.

At the same time:
- do not annex countries arbitrarily
- do not erase meaningful geopolitical texture for convenience

---

## Map and State Ownership

Treat map and state ownership carefully.

When working on ownership:
- verify state history directly
- verify country history directly
- check for duplicate or contradictory owner/controller lines
- check startup events, focuses, decisions, and scripted effects that alter ownership
- preserve intended borders unless the issue is clearly broken
- distinguish direct map edits from territorial setup edits

Do not make speculative map redesigns to resolve logs.

---

## Formatting and Maintainability

AOTA should move toward consistent, maintainable formatting.

Preferred standards:
- multiline formatting for complex script blocks
- consistent indentation
- readable block structure
- clear delimiters
- logically grouped definitions
- avoid one-line compressed files where safe to normalize

Treat one-line or structurally compressed HOI4 files as maintainability liabilities.

When normalizing:
- preserve logic exactly unless a clear fix is intended
- do not accidentally rewrite behavior while reformatting

---

## File and Folder Expectations

Important folders include:
- `common/`
- `events/`
- `history/`
- `localisation/`
- `interface/`
- `gfx/`
- `map/`
- `version_history/reports/`
- `version_history/error_logs/raw/`
- `version_history/error_logs/parsed/`

### Descriptor expectations
For local launcher use:
- outer `.mod` file should be next to the live mod folder in the HOI4 mod directory
- `descriptor.mod` should be inside the actual AOTA folder
- path and folder name must match exactly
- preserve `version` and `supported_version` unless explicitly fixing malformed setup and no safer option exists

---

## Validation Expectations

After making changes:
- re-check changed files for syntax
- re-check changed references
- verify no obvious neighboring breakage was introduced
- verify changed focus/event/decision/idea links still line up
- verify localisation keys exist where touched
- verify AI logic where touched
- verify descriptor/path correctness when relevant

If validation tooling is available, use it.
If not, perform strong manual reference and syntax validation.

---

## Reporting Standards

When asked to report, always include:
- what was reviewed
- what was changed
- why it was changed
- what remains unresolved
- whether unresolved issues are ambiguous, lore-sensitive, or playtest-dependent
- which files/systems were affected

Separate findings into:
- hard blockers
- major issues
- medium issues
- minor warnings / noise
when applicable

Do not give soft approvals.
Be honest and explicit.

---

## How to Handle Ambiguity

If the intended outcome is unclear:
- do not invent sweeping fixes
- do not pretend certainty
- document ambiguity
- preserve future options
- prefer a narrow repair
- leave a manual-review note if needed

Ambiguous issues should be labeled clearly, not silently papered over.

---

## What “Good” Looks Like

The target standard for AOTA is:
- launch-correct
- parser-clean or materially improved toward parser cleanliness
- structurally disciplined
- maintainable
- ideologically coherent
- AI-usable
- lore-consistent
- ambitious without being sloppy
- technically closer to a polished large HOI4 overhaul

The goal is not perfection through simplification.
The goal is strong technical discipline without sacrificing the scope of the mod.

---

## Default Prompt Interpretation Rules

When a task asks for:
- **audit** → inspect broadly, classify findings, report cleanly, do not over-edit unless told
- **fix** → act directly on safe issues, validate touched systems, report what changed
- **plan** → produce a structured roadmap with priorities and dependencies
- **rework** → preserve concept, improve execution, avoid content gutting
- **compare to Kaiserreich** → use KR as a standards benchmark, not a content donor
- **use error logs** → newest raw AOTA logs are source of truth, older AOTA logs are context only

---

## Final Standing Rule

When in doubt:
- preserve AOTA’s identity
- preserve content breadth
- prefer root-cause fixes
- prefer maintainable structure
- fix obvious technical problems immediately
- be conservative in lore-sensitive areas
- do not leave easy parser/reference problems unfixed
- do not hide unresolved issues