<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/header-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="assets/header-light.svg">
  <img alt="Aleksandrs Drozdovs, software engineer, Dublin, Ireland" src="assets/header-light.svg" width="840">
</picture>

Computer Science and Software Engineering graduate, Maynooth University, 2026. Based in Dublin, available now.
Graduate software engineering and quantitative developer roles, Dublin or remote across the EU and UK.

[Portfolio](https://aleksandrs-portfolio.vercel.app) · [CV](https://aleksandrs-portfolio.vercel.app/cv.pdf) · [LinkedIn](https://www.linkedin.com/in/aleksandrsdrozdovs/) · [Email](mailto:aleksandrs.drozdovs2005@gmail.com)

## Merged upstream

Fixes shipped into other teams' codebases, reviewed by their maintainers and held to their test suites. Each link is the pull request itself.

- **hflow** (Hebbian Robotics) [#288](https://github.com/Hebbian-Robotics/hflow/pull/288): a dedicated exception and failure kind so transform content refusals stop being retried as infrastructure errors.
- **narwhals** [#3856](https://github.com/narwhals-dev/narwhals/pull/3856): the pandas-like backend ignored the `schema` argument's column selection and order in `from_dicts`; fixed with six new tests, each proven failing first.
- **exchange_calendars** [#593](https://github.com/gerrymanoim/exchange_calendars/pull/593): the Dubai Financial Market (XDFM) calendar from scratch, sourced from DFM and Nasdaq Dubai circulars and bounded at the 2022 UAE work-week switch.
- **holidays** [#3748](https://github.com/vacanza/holidays/pull/3748): Russian localisation for Latvia's holiday calendar, native-speaker translation.
- **yfinance** [#2936](https://github.com/ranaroussi/yfinance/pull/2936): traced a suspected timezone regression to an intentional, changelogged change, then fixed the real gap in the `download()` docstring.

Nine more fixes are open under maintainer review across scipy, splink, uvicorn, duckdb-python, quantstats, and soccerdata.

## Systems

**[jobq](https://github.com/aleks-drozy/jobq)** · Go, standard library only
Durable job queue from scratch: at-least-once delivery, actor-per-topic concurrency, leases, retries, dead-letter queues, and a CRC-checked, group-committed write-ahead log (550µs to 65µs per op under 16 producers). A crash harness kills the process cold mid-write across five rounds: zero acknowledged jobs lost, zero resurrected. Conservation and unique-settlement invariants hold under the race detector.

**[Options pricing engine](https://github.com/aleks-drozy/options-pricing-engine)** · [live explorer](https://aleks-drozy.github.io/options-pricing-engine/)
Black-Scholes, CRR binomial (European and American) and seeded Monte Carlo pricers cross-validated through seven machine-checked numerical gates (put-call parity to 2.84e-14). Inverts a real SPY option chain to implied volatility and recovers the smile. The explorer re-runs all seven gates on every page load.

**[Jarvis](https://github.com/aleks-drozy/jarvis)** · Electron, whisper.cpp, PowerShell, Claude agent
Desktop assistant with fully on-device speech-to-text and a scheduled, unattended agent pipeline that delivers a daily 08:30 Telegram briefing. Two-way commands over a closed whitelist locked to one chat ID, failing closed on an unknown sender. CI green on windows-latest, gitleaks over the full history.

## Data engineering

**[registry-resolve](https://github.com/aleks-drozy/registry-resolve)** · Python, Splink, DuckDB
Entity resolution across three real Irish open-data registers (821k CRO companies, the Register of Charities, public procurement awards). Deterministic ID joins first, probabilistic matching for the residual, evaluated against 330 blind human-labelled pairs. 224 tests.

**[irish-property-price-index](https://github.com/aleks-drozy/irish-property-price-index)** · dbt, DuckDB · [live dashboard](https://aleks-drozy.github.io/irish-property-price-index/dashboard/)
Mix-adjusted stratified-median price index over all 797,774 sales in the Property Price Register, 14 dbt models and 91 dbt tests, validated against the CSO's official index. Finding: the raw median overstates national growth by 2.22 index points and understates Dublin's by 3.91.

## Research that publishes its own negative results

The hypothesis and the pass/fail gate are written and committed first, then the analysis runs. Five of these have a verdict; all five are published as they came out, and no threshold was widened once the result went the wrong way.

**[fyp-strategy-engine](https://github.com/aleks-drozy/fyp-strategy-engine)**, verdict DISPROVEN
Six-phase test of a strategy whose headline backtest was +$28,400. The configuration is hash-frozen and the runner refuses to start on a mismatch. 17 walk-forward folds per instrument across ~10 years of CME index futures: pooled profit factor 0.905 over 1,402 out-of-sample trades, 90% upper bound below breakeven. 176 tests in CI. The gates also caught a 60-minute timestamp bug in the source dataset.

**[alpha-signal-lab](https://github.com/aleks-drozy/alpha-signal-lab)**, verdict NULL · [dashboard](https://aleks-drozy.github.io/alpha-signal-lab/)
LightGBM versus plain momentum on 5-day cross-sectional equity returns under purged walk-forward CV and eight automated leakage audits. A deliberately leaky twin shows the gap: honest rank IC 0.0100 versus 0.1506. The honest model does not beat momentum; a SHAP diagnostic explains why.

**[prompt-placebo](https://github.com/aleks-drozy/prompt-placebo)**, verdict PLACEBO
Pre-registered, paired-delta audit of six prompting techniques across 1,438 questions and 23,008 API requests. 0 of 39 comparisons still work on 2026 reasoning models; the only two effects to survive Holm-Bonferroni correction are harms.

**[football-trajectory](https://github.com/aleks-drozy/football-trajectory)**, verdict NOT PROVEN · [live explorer](https://aleks-drozy.github.io/football-trajectory/)
Monte Carlo career projection over 24,057 FBref player-seasons. Real skill at every horizon, but the 80% intervals cover ~90%, so it fails its own calibration gate by being under-confident and ships labelled that way. 95 tests.

**[polymarket-favourite-bias](https://github.com/aleks-drozy/polymarket-favourite-bias)**, verdict NOT PROVEN
2,418 resolved markets: favourites win 90.6% of the time and still return −0.98% after fees, with a bootstrap interval spanning breakeven. The gate was the repository's first commit.

**[dublin-bikes-forecast](https://github.com/aleks-drozy/dublin-bikes-forecast)**, verdict pending, paused
Twice-daily P(bike)/P(dock) forecasts for ~115 stations, each git-committed before its target time and scored against pre-registered baselines. Paused since 23 July 2026 when the cloud host suspended the VM; the ledger shows the gap rather than restarting the clock.

## Stack

| | |
| --- | --- |
| **Languages** | Python, TypeScript, JavaScript, Go, SQL, Java, C++, PowerShell |
| **Backend and data** | FastAPI, Node, Express, Supabase (Postgres, RLS), DuckDB, dbt, MongoDB |
| **Frontend** | React, Next.js, Tailwind, Electron |
| **Research** | pandas, NumPy, scikit-learn, LightGBM, SHAP, walk-forward validation, bootstrap and permutation inference, pre-registration |
| **Testing and CI** | pytest, Vitest, Playwright, Go race detector, property-based and crash-injection tests, GitHub Actions |
| **AI** | LLM integration (Anthropic, Groq), agents and tool use (MCP, Claude Code), local inference with whisper.cpp |

**Education**: B.Sc. (Hons) Computer Science and Software Engineering, Maynooth University, 2026, 2:1 Honours.
**Experience**: Quantitative Researcher and Software Engineer, DLT Capital, February to July 2025 (~$15K live trading profit from systematic strategies).

I use Claude Code as a pairing partner; the co-author trailers in these histories say so. Every method choice, architecture call, and verdict is mine, and I can walk through the reasoning on any commit.
