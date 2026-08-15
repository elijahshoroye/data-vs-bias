# PROJECT CONSTITUTION — DATA vs. BIAS

This document is the contract the project has to obey. If a future decision contradicts this document, the document wins, not the decision — unless the document is deliberately amended, with the amendment logged in `PROJECT_LOG.md`.

## 1. Objective

Build a transparent, reproducible model that estimates Manchester United's probability of winning the 2026/27 Premier League, publish the preseason estimate before results can bias it, update the estimate as the season progresses, and score the model's accuracy at the end of the season against what actually happened.

The deliverable is not "a number that says United will win." The deliverable is a documented process that produces *a* number, whatever that number turns out to be, and a public record of whether that number was any good.

## 2. Research Questions

Central question: Can historical and current football data be used to estimate Manchester United's probability of winning the 2026/27 Premier League?

Supporting questions live in `QUESTIONS.md` and will grow over the project. They are grouped into three tiers: historical baseline (what does a champion look like), current-team diagnostic (where does United sit against that baseline), and predictive (how do you turn team strength into a title probability).

## 3. Analytical Philosophy

- Sequence matters: baseline before diagnosis, diagnosis before modelling, modelling before simulation. Do not skip ahead to Monte Carlo or ML because it's more exciting than descriptive statistics — descriptive statistics is what tells you if the fancy model is even measuring the right thing.
- Every claim traces to a number, and every number traces to a query or calculation you can re-run. "United look better this season" is not an analytical claim until it's backed by a specific metric, computed from specific data, over a specific window.
- Prefer the boring correct method over the impressive fragile one. A well-validated linear model beats an overfit neural net on 10 seasons of data, every time.
- Uncertainty is a first-class output, not an afterthought. A probability estimate without a confidence interval or a stated method is closer to a guess.

## 4. Data Principles

- No fabricated data, ever. If a stat is missing, the record says "missing," not an inferred or invented placeholder value dressed up as real.
- Every dataset gets a documented source, access date, and license/usage terms before it's used, in `docs/`.
- Raw data in `data/raw/` is never edited in place. Cleaning steps are scripted (not manual spreadsheet edits) and reproducible, output goes to `data/cleaned/`, and feature-engineered analysis tables go to `data/processed/`. If you can't regenerate `processed/` from `raw/` by rerunning a script, the pipeline is broken.
- Sample size gets stated next to every historical claim. "Champions since 2010 average X points" needs the reader to know that's ~15 data points, not 1,500.

## 5. Modelling Principles

- Start with the simplest model that could plausibly work (e.g., historical points/PPG distribution, basic strength ratings) before adding complexity. Complexity has to earn its place by measurably improving out-of-sample accuracy.
- Every model gets validated against data it wasn't trained on. A model that only explains the past is not a predictive model.
- Model assumptions are written down explicitly, in plain language, next to the model. "This assumes team strength is stable within a season" is a sentence someone with no stats background can evaluate and disagree with.
- When multiple modelling approaches are viable, the tradeoffs get written out before picking one — this is a place where the mentor role in this project pushes back rather than defaulting to whatever's fastest to code.

## 6. Version-Control Principles

- The project lives in Git from the first working commit. Every meaningful change (new data pulled, cleaning step added, model version changed) is its own commit with a message that explains *why*, not just *what*.
- Data files above a reasonable size threshold, virtual environments, and notebook checkpoints do not get committed — see `.gitignore`. Raw data provenance is documented instead of the raw file itself being force-committed if it's large.
- The preseason prediction gets tagged (e.g. `v1.0-preseason`) before a single 2026/27 match is played, so it is provably locked in before results exist. Any later prediction update is a new, dated version — the old one is never edited or deleted.

## 7. Content Philosophy

- Public-facing content (YouTube, TikTok, Instagram, LinkedIn, X, Facebook — drafted under `content/`) reports what the analysis found, not what would perform well with a fan audience. If the honest headline is "United are unlikely to win the league," that is the headline.
- Content is allowed to show the tension between fan identity and analyst output explicitly — that tension is the hook, not something to be hidden or resolved artificially in United's favor.
- No content gets published before the underlying analysis it references is finished and checked. Draft-ahead-of-data is how bias sneaks in.

## 8. Limitations

To be stated honestly, not hedged into meaninglessness:

- Football has a low sample size per season (38 games) and high variance — even a genuinely strong team can miss the title on randomness (injuries, red cards, refereeing, individual mistakes). A probability model can be well-calibrated and still be "wrong" in a single-season outcome.
- Historical champion profiles are backward-looking. The Premier League's competitive dynamics change (financial rules, managerial cycles, opponent quality), so a profile built on 2010-2025 seasons is not guaranteed to hold in 2026/27.
- Transfer windows, injuries, and managerial changes during the season are hard-to-quantify inputs. The model's early-season version will be weaker than its later-season version by construction — this should be reported, not smoothed over.
- The analyst (me) is a Manchester United supporter. That is a standing conflict of interest for every subjective modelling choice (which features to include, which seasons to weight, how to handle outliers). Section 9 exists because of this, not despite it.

## 9. Rules Against Confirmation Bias

- **If the model says Manchester United have a low probability of winning the league, we report it rather than manipulate the model.** This is the single non-negotiable rule of the project.
- Model structure and feature choices are decided *before* looking at how they affect United's specific number, wherever practical. If a modelling choice is made and it happens to move United's probability up, that gets flagged and scrutinized harder, not accepted quietly.
- Any change to the model after the preseason prediction is published must be logged in `PROJECT_LOG.md` with the reason, and must be shown to affect all 20 clubs' numbers consistently — not tuned to move United's number specifically.
- Predictions are versioned and timestamped (Section 6). You cannot quietly revise a bad preseason call after the season provides hindsight.
- At season end, the model gets scored on accuracy (e.g., calibration against actual outcomes across the league, not just "did United win"). A model that was right about United by accident, while being wrong about the rest of the league, is a bad model.
- When an analytical decision has more than one defensible approach, alternatives get written down with their tradeoffs before one is chosen, and the choice is justified on methodological grounds — never on "which one makes United look better."
