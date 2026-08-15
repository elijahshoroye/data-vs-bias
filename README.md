# DATA vs. BIAS

**Central question:** Can historical and current football data be used to estimate Manchester United's probability of winning the 2026/27 Premier League?

This is a data analytics portfolio project. It is also a personal experiment: I am a Manchester United fan building a model that is allowed to disagree with me. See `PROJECT_CONSTITUTION.md` for the rules that govern that tension.

## Status

Setup stage. No analysis has been run yet. No data has been collected yet. Anything beyond folder structure and documentation in this repo has not happened — check `PROJECT_LOG.md` for the actual session-by-session record before assuming otherwise.

## Structure

```
DATA-VS-BIAS/
    data/
        raw/          # untouched source data, exactly as downloaded
        cleaned/       # cleaned but not yet feature-engineered
        processed/     # analysis-ready tables
    notebooks/         # exploratory Jupyter notebooks
    src/                # reusable Python modules (scraping, cleaning, modelling)
    dashboards/         # any dashboard code/exports
    visuals/            # exported charts/figures
    content/            # platform-specific drafts for publishing project updates
        youtube/
        tiktok/
        instagram/
        linkedin/
        x/
        facebook/
    docs/               # supplementary write-ups, methodology notes
    README.md
    PROJECT_CONSTITUTION.md   # philosophy, principles, anti-bias rules
    PROJECT_LOG.md             # running journal of actual work done
    QUESTIONS.md                # research question backlog
    requirements.txt
    .gitignore
```

## Milestone 1 (current)

Analyse ~10-15 previous Premier League seasons and establish the statistical profile of a champion: points, PPG, W/D/L, goals scored/conceded, goal difference, home vs. away split. No modelling until this baseline exists.

## Principles (short version)

If the model says Manchester United are unlikely to win the league, that result gets published, not adjusted. Full reasoning in `PROJECT_CONSTITUTION.md`.
