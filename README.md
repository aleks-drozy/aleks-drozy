<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/header-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="assets/header-light.svg">
  <img alt="Aleksandrs Drozdovs — software engineer, Dublin, Ireland" src="assets/header-light.svg" width="840">
</picture>

Computer Science and Software Engineering, Maynooth University, 2026. Based in Dublin.  
Open to graduate software engineering roles.

[Portfolio](https://aleksandrs-portfolio.vercel.app) · [LinkedIn](https://www.linkedin.com/in/aleksandrsdrozdovs/) · [Email](mailto:aleksandrs.drozdovs2005@gmail.com)

## Shipped

**[Trading Dashboard](https://github.com/aleks-drozy/Trading_Dashboard)** · [live](https://tradingdashboard-one.vercel.app)  
Trade journal and analytics app. Next.js 16 and TypeScript on Vercel with a FastAPI service on Render. 232 commits, 113 automated tests across both languages, NextAuth with Google OAuth and a credentials provider, unauthenticated API routes rejected at the edge.

**[Jarvis](https://github.com/aleks-drozy/jarvis)**  
Windows desktop assistant with an Electron HUD. Speech-to-text runs entirely on-device through a vendored whisper.cpp binary, with no cloud transcription anywhere in the codebase. Delivers a daily 08:30 Telegram briefing and accepts two-way commands over a closed whitelist locked to a single chat ID, failing closed on an unknown sender. CI green on windows-latest across 17 PowerShell suites, with gitleaks scanning the full history.

**[Backtest engine](https://github.com/aleks-drozy/aleksander-backtest-engine)**  
Walk-forward backtester for nine strategy modules on a vectorised pandas and NumPy P&L core. 42 tests green in CI. Reports Probabilistic Sharpe Ratio, Monte Carlo permutation p-values, and cost sensitivity at 1x, 2x and 4x. A weekly cron workflow refetches the data, reruns everything and commits the results, so the published numbers cannot go stale unnoticed.

**[Speed-to-lead prototype](https://github.com/aleks-drozy/speed-to-lead-demo)** · [live demo](https://aleks-drozy.github.io/speed-to-lead-demo/)  
Interactive prototype of a lead-qualification flow for a trades business: marketing page, chat widget and owner dashboard in one self-contained HTML file, no build step and no dependencies. The conversation is a deterministic state machine, not a model call.

## Research that publishes its own negative results

Three studies where I wrote the hypothesis and the pass/fail gate first, committed them, then ran the analysis. All three came back negative, and all three are published that way. The decision rule was fixed before the data could argue with it, the artefacts are committed so every number recomputes, and no threshold was quietly widened once the result went the wrong way.

**[Futures strategy engine](https://github.com/aleks-drozy/fyp-strategy-engine)** — verdict: DISPROVEN  
Tested a strategy whose headline track record was +$28,400. The configuration is frozen in a hash-gated file committed three minutes before the runner that consumes it, and the runner recomputes the hash and refuses to start on a mismatch, so the pre-registration is checkable from git metadata rather than asserted in prose. 17 walk-forward folds per instrument across ~10 years of CME index futures and 10.1M validated 1-minute bars. Pooled profit factor 0.905 over 1,402 out-of-sample trades across two independent instruments, with a 90% upper bound below breakeven. 176 tests, 168 passing and 8 skipped in CI.

**[Football trajectory](https://github.com/aleks-drozy/football-trajectory)** · [live explorer](https://aleks-drozy.github.io/football-trajectory/) — verdict: NOT PROVEN  
Monte Carlo career projection over 24,057 FBref Big-5 player-seasons, separating talent, ageing and minutes into three distinct sources of uncertainty. It fails its own calibration gate by being under-confident, and ships the headline projection labelled NOT TRUSTWORTHY rather than widening the gate to pass. 95 tests in CI. `PREDICTIONS.md` freezes 16 named forward calls with 80% intervals and four fixed scoring rules, to be scored publicly after the 2026-27 season.

**[Polymarket favourite bias](https://github.com/aleks-drozy/polymarket-favourite-bias)** — verdict: NOT PROVEN  
2,418 resolved prediction markets. Favourites win 90.6% of the time and still return −0.98% after fees, with a bootstrap interval spanning breakeven, which the writeup reports as inconclusive rather than rounding to an edge. The gate was the repository's first commit, roughly 16 hours before the backtest ran. 78 tests, no network calls, and the full funnel from 12,405 markets down to 2,418 published as itemised CSV rather than prose.

## Stack

| | |
| --- | --- |
| **Languages** | Python, TypeScript, JavaScript, SQL, Java, C++, PowerShell |
| **Frontend** | React, Next.js, Tailwind, Vite, Electron |
| **Backend** | FastAPI, Node, Express, Supabase, MongoDB |
| **Research** | pandas, NumPy, SciPy, Jupyter, walk-forward validation, bootstrap and permutation inference |
| **Testing** | pytest, Vitest, Pester, golden-fixture and lookahead-bias regression tests |
| **Infra** | Git, GitHub Actions, Vercel, Render, GitHub Pages |
| **AI** | LLM integration (Anthropic, Groq), agents and tool use (MCP), local inference with whisper.cpp |

---

**Education** — B.Sc. (Hons) Computer Science and Software Engineering, Maynooth University, 2026. Upper Second-Class Honours.  
**Experience** — Quantitative Researcher and Software Engineer, DLT Capital, February to July 2025.
