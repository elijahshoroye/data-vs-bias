# PROJECT LOG

Running journal. One entry per working session. Entries record what actually happened — not what was planned, not what's aspirational. If something didn't get done, it's logged as not done.

Template for new entries:

```
## YYYY-MM-DD — [session title]

**Objective:**

**Work completed:**

**Skills learned:**

**Problems encountered:**

**Decisions made:**

**Files changed:**

**Next steps:**
```

---

## 2026-08-15 — Project setup

**Objective:** Stand up the DATA-VS-BIAS project workspace and governing documents before any data or analysis work begins.

**Work completed:**
- Confirmed connected folder (`MUFC_PL_26:27`) was empty; no existing project files were at risk of being overwritten.
- Created full directory structure: `data/{raw,cleaned,processed}`, `notebooks/`, `src/`, `dashboards/`, `visuals/`, `content/{youtube,tiktok,instagram,linkedin,x,facebook}`, `docs/`.
- Wrote `README.md`, `PROJECT_CONSTITUTION.md`, `PROJECT_LOG.md` (this file), `QUESTIONS.md`, `requirements.txt`, `.gitignore`.

**Skills learned:** N/A — this was a setup session, not an analysis session.

**Problems encountered:** The code-execution sandbox used to run shell commands (Python, Git, etc.) was unavailable this session due to a sandbox disk-space error. This means `python3 --version` and `git --version` were not confirmed to be available or absent, and no `git init` was run. This needs to be resolved and confirmed in the next session before any coding work starts.

**Decisions made:** Nested the project under `DATA-VS-BIAS/` inside the already-connected `MUFC_PL_26:27` folder, per explicit confirmation, rather than treating the connected folder itself as project root.

**Files changed:** All files listed under "Work completed" above — all newly created, nothing overwritten.

**Next steps:**
1. Confirm Python and Git are available in the working environment; run `git init` and make the first commit.
2. Identify and vet a source for ~10-15 seasons of Premier League final-table data (points, W/D/L, GF/GA, home/away split). Do not proceed with analysis until the source is confirmed appropriate and documented in `docs/`.
3. Begin Milestone 1: compute the statistical profile of a Premier League champion.
