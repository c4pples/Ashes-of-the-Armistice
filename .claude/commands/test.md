# /test — Launch HOI4 and Diagnose AOTA Errors

Launch HOI4 through Steam, wait for it to close, then read the logs and diagnose any AOTA errors or crashes.

## Steps

### 1. Launch HOI4 via Steam

Run this bash command to launch:

```bash
cmd.exe /c "start steam://rungameid/394360"
```

Tell the user: "HOI4 launched. Play or load a save, then close the game when done."

### 2. Wait for HOI4 to start

Poll every 10 seconds (up to 3 minutes) until `hoi4.exe` appears in the process list:

```bash
tasklist.exe 2>/dev/null | grep -i "hoi4.exe"
```

If HOI4 never starts within 3 minutes, tell the user and stop.

### 3. Wait for HOI4 to close

Once HOI4 is running, poll every 15 seconds until `hoi4.exe` is gone from the process list. Tell the user "Waiting for HOI4 to close..." once at the start of this wait.

### 4. Copy logs into the mod's error log folder

Copy the current logs into `version_history/error_logs/raw/` with a timestamped filename so they are preserved:

```bash
TIMESTAMP=$(date +"%Y%m%d_%H%M%S")
cp "/c/Users/dirks/Documents/Paradox Interactive/Hearts of Iron IV/logs/game.log" \
   "/c/Users/dirks/Documents/Paradox Interactive/Hearts of Iron IV/mod/AOTA/version_history/error_logs/raw/game_${TIMESTAMP}.log"
cp "/c/Users/dirks/Documents/Paradox Interactive/Hearts of Iron IV/logs/error.log" \
   "/c/Users/dirks/Documents/Paradox Interactive/Hearts of Iron IV/mod/AOTA/version_history/error_logs/raw/error_${TIMESTAMP}.log" 2>/dev/null || true
```

### 5. Read and analyze the logs

Read the following files:
- `/c/Users/dirks/Documents/Paradox Interactive/Hearts of Iron IV/logs/game.log`
- `/c/Users/dirks/Documents/Paradox Interactive/Hearts of Iron IV/logs/error.log`

Focus on:
- Crash reports and fatal errors (hard blockers)
- Script errors referencing AOTA files (`mod/AOTA/`)
- Missing file / bad path references
- Parser errors (bad syntax, unexpected tokens)
- Missing localisation keys
- Missing or broken event / focus / decision references
- Missing sprite or GFX references
- Duplicate definitions
- Any error that appears more than 5 times (spam = root cause)

Ignore vanilla HOI4 errors that are not in AOTA files.

### 6. Diagnose and report

Produce a structured diagnosis with these sections:

**Crash cause** (if the game crashed — what triggered it)

**Hard blockers** — errors that prevent launch or cause crashes

**Major errors** — broken references, bad syntax, missing links

**Warnings / noise** — repeated minor spam, low-impact issues

**Files affected** — list the AOTA files involved

For each issue, state:
- What the error is
- Which file and line (if available)
- What the likely cause is
- Whether it is safe to fix automatically

### 7. Fix safe issues directly

Without asking, fix issues that are clearly safe per the AOTA CLAUDE.md safe-to-fix list:
- malformed syntax / bad braces
- broken paths
- obvious typos in references
- broken localisation links where the intended key is obvious
- dead asset references
- obvious duplicate scripting mistakes
- missing namespace declarations where intent is obvious

For each fix made, note it in the report.

### 8. Save the report

Write the diagnosis report to:
`version_history/reports/test_run_TIMESTAMP.md`

Use the same timestamp as the log copy.

### 9. Commit and push

Stage all changed files, commit with a message summarizing what was fixed, and push to origin/main:

```bash
git add -A
git commit -m "Fix: post-test-run error log pass [TIMESTAMP]"
git push origin main
```

If there is nothing to commit, tell the user the mod is clean.

### 10. Summary to user

Tell the user:
- Whether HOI4 crashed or exited cleanly
- How many errors were found (broken down by severity)
- How many were auto-fixed
- What still needs manual attention
- Where the report was saved
