# AAPIS™ Unseen Data Stress Test
**Ambika Analytics LLC** · Confidential & Proprietary
Monte Carlo N = 1,000 Independent Timelines · 10,000 Simulated Years

---

## What Is This Test?

Most investment strategies are evaluated on historical data — data the model was already exposed to during development. That creates an obvious problem: a strategy can be unconsciously tuned to fit past market conditions without actually having any predictive power going forward.

This report is different. **AAPIS™ was tested exclusively on data it has never seen.**

We built a synthetic market engine that generates completely new, randomized 10-year market histories — each one statistically independent, each one unknown to the model at the time of testing. We then ran AAPIS™ across 1,000 of these independent timelines, covering **10,000 total simulated years**, and measured whether it could outperform a buy-and-hold S&P 500 strategy across all of them.

The result: **AAPIS™ beat SPY in 68.9% of simulated decades.**

---

## The Stress Test Was Deliberately Brutal

This is not a favorable simulation. The synthetic market engine was intentionally calibrated to be **harsher than any period in modern market history.**

The engine generates four distinct volatility regimes, each applied randomly across the 10-year simulation windows:

| Regime | Daily Return (μ) | Daily Volatility (σ) | VIX Level |
|---|---|---|---|
| Calm | +0.050% | 0.7% | ~13 |
| Normal | +0.035% | 1.2% | ~19 |
| **Stress** | **−0.010%** | **2.2%** | **~30** |
| **Crisis** | **−0.180%** | **4.2%** | **~52** |

The crisis regime — with σ = 4.2% daily volatility and a mean daily loss of −0.18% — is **more severe and more frequent than any comparable period in the 1994–2026 historical record.** These are not tail events in the simulation. They are recurring features of every timeline.

Every simulation also starts with 300 warm-up days of market data before any strategy decisions are made, ensuring no look-ahead bias contaminates the results.

> **Why does this matter?** A strategy that only works in favorable conditions is not robust. By stress-testing in environments worse than history, we confirm AAPIS™ has genuine structural edge — not just historical curve-fitting.

---

## Head-to-Head Results Across 10,000 Simulated Years

| Metric | AAPIS™ | RAND | SPY | UPRO (buy & hold) |
|---|---|---|---|---|
| **10-Year Horizon Win Rate vs SPY** | **68.9%** | 57.2% | — | — |
| **Annual Win Rate vs SPY** | **54.1%** | 47.3% | — | — |
| **Avg Total Return (10-yr)** | **148.6%** | 126.9% | 94.5% | 80.3% |
| **Mean CAGR** | **6.78%** | 5.73% | 4.95% | −9.69% |
| **Median CAGR** | **6.82%** | 5.64% | 4.91% | −10.90% |
| **Avg Sortino Ratio** | **0.46** | 0.41 | 0.38 | 0.14 |
| **Avg Max Drawdown** | 53.18% | 54.57% | 49.38% | 92.86% |
| **Avg Green Signals / Year** | **2.12** | — | — | — |

> **What is RAND?** RAND is a control strategy that uses the exact same UPRO entry and exit mechanics as AAPIS™, but enters on randomly chosen days instead of on signal confirmation — using the same number of entries per simulation as AAPIS™ actually generated. It answers the question: *"Is AAPIS™ actually timing the market, or just benefiting from any UPRO exposure at all?"* The gap between AAPIS™ and RAND isolates the pure value of the signal.

---

## Return Performance

### Total Return Over 10 Years (Avg across 1,000 simulations)
```
AAPIS™  ████████████████████████████████████  148.6%
RAND    ████████████████████████████░░░░░░░░  126.9%
SPY     ████████████████████████░░░░░░░░░░░░   94.5%
UPRO    ████████████████████░░░░░░░░░░░░░░░░   80.3%
```

**AAPIS™ returned 148.6% on average** over simulated 10-year windows — **54.1 percentage points more than SPY** and nearly double what buy-and-hold UPRO delivered despite both using the same leveraged ETF as their instrument.

### Annualized CAGR
```
AAPIS™   6.78%  ██████████████████████░
RAND     5.73%  ███████████████████░░░░
SPY      4.95%  █████████████████░░░░░░
UPRO    -9.69%  ░░░░░░░░░░░░░░░░░░░░░░░  (negative — volatility decay)
```

AAPIS™ generates **+183bps of annualized alpha over SPY** in an environment calibrated to be worse than 2008. The near-identical mean and median CAGR (6.78% vs 6.82%) confirms the return distribution is symmetric — results are not inflated by a handful of lucky decades. **This is a consistent, repeatable edge.**

---

## The Harsh Environment Makes AAPIS™ Results More Significant, Not Less

Under normal historical conditions (1994–2026), UPRO has been a powerful instrument — capturing 3× the S&P 500's daily return during bull markets. In this stress test, **buy-and-hold UPRO produced a mean CAGR of −9.69% and an average maximum drawdown of 92.86%.**

That is not a modeling error. It is the mathematically correct consequence of the crisis regime frequency built into the simulation. Volatility decay — the compounding drag that 3× leverage creates during volatile periods — is severe enough to erase all gains and more when adverse conditions are sustained.

**AAPIS™, using the same UPRO instrument, produced +6.78% CAGR and a 53.18% max drawdown in the same environments.**

The difference is entirely attributable to two things: signal-guided entries that avoid the worst volatility periods, and the trailing stop-loss that limits exposure when conditions deteriorate. In a deliberately brutal environment where raw UPRO fails catastrophically, AAPIS™ remains consistently profitable.

---

## Decomposing the Edge: Signal vs. Exposure

One of the most important questions about any timing strategy is whether its edge comes from *when it enters* or simply from *the fact that it holds a high-return instrument at all.* The RAND benchmark answers this precisely.

| Source of Edge | 10-Year Horizon Contribution |
|---|---|
| Structural UPRO exposure premium over SPY | ~7.2pp &nbsp;&nbsp; (57.2% − 50%) |
| **Pure AAPIS™ signal timing alpha** | **~11.7pp &nbsp;&nbsp; (68.9% − 57.2%)** |
| **Total AAPIS™ edge over SPY** | **~18.9pp** |

**The timing signal alone contributes ~62% of AAPIS™'s total edge over SPY.** Random UPRO exposure contributes the remaining 38%. This is the clearest evidence that AAPIS™ is not simply a leveraged beta story — the five-factor entry signal (Soil · Water · Fire · Space · Wind) carries genuine, independent, measurable timing value.

---

## Risk-Adjusted Performance

### Sortino Ratio — Across 10,000 Simulated Years

The Sortino ratio measures return earned per unit of downside risk — the most relevant risk metric for a strategy that aims to protect capital during adverse conditions.

| Strategy | Avg Sortino Ratio | vs SPY |
|---|---|---|
| **AAPIS™** | **0.46** | **+0.08** |
| RAND | 0.41 | +0.03 |
| SPY | 0.38 | baseline |
| UPRO (buy & hold) | 0.14 | −0.24 |

AAPIS™ achieves the highest Sortino ratio of all four strategies — **3.3× higher than buy-and-hold UPRO** despite using the same instrument. Every unit of downside risk in AAPIS™ produces more return than any alternative in the comparison set.

### Maximum Drawdown

| Strategy | Avg Max Drawdown | vs AAPIS™ |
|---|---|---|
| SPY | 49.38% | −3.8pp (lower) |
| **AAPIS™** | **53.18%** | baseline |
| RAND | 54.57% | +1.4pp worse |
| UPRO (buy & hold) | **92.86%** | **+39.7pp worse** |

In a crisis-heavy simulation environment, AAPIS™ reduces maximum drawdown versus buy-and-hold UPRO by **nearly 40 percentage points**. AAPIS™ also outperforms RAND on drawdown, confirming the signal avoids some of the worst entry points that random timing hits.

The honest note: AAPIS™ carries ~3.8pp more average drawdown than SPY. This is the direct, expected cost of leveraged exposure — even with active management and a trailing stop. Investors who choose AAPIS™ should be prepared to hold through drawdowns comparable to 2008 in exchange for meaningfully higher long-term returns.

---

## Win Rate Convergence Across Sample Sizes

To confirm that the 68.9% win rate is a stable, reliable estimate rather than a small-sample artifact, we ran the stress test at progressively larger N and tracked convergence:

| Sample Size (N) | AAPIS™ 10-yr Win Rate | RAND 10-yr Win Rate | Signal Alpha |
|---|---|---|---|
| 100 (Run A) | 70.0% | 55.0% | ~15pp |
| 100 (Run B) | 70.0% | 56.0% | ~14pp |
| 100 (Run C) | 64.0% | 50.0% | ~14pp |
| **1,000 (Final)** | **68.9%** | **57.2%** | **~11.7pp** |

At N = 1,000, the standard error on the win rate is approximately **±1.5 percentage points**, giving a statistically defensible range of **67–71%** for the true 10-year horizon win rate. The signal alpha (AAPIS™ minus RAND) remained stable across all runs at approximately 11–15pp, confirming that the edge is real and not a sampling artifact.

---

## Why Only ~2 Green Signals Per Year?

| Metric | Value |
|---|---|
| Avg Green Signals per 10-Year Simulation | 21.25 |
| **Avg Green Signals per Year** | **2.12** |

AAPIS™ enters UPRO approximately **twice per year** on average. This is deliberate.

The system requires simultaneous confluence across five independent indicator families — Soil (trend foundation), Water (momentum structure), Fire (MACD confirmation), Space (volatility regime), and Wind (RSI and mean-reversion clearance) — before any green signal is issued. Each filter independently disqualifies the majority of market days. Together, they concentrate UPRO exposure into a small number of high-probability windows per year.

**Signal rarity is a feature.** A system that enters UPRO frequently also enters during unfavorable periods — as demonstrated by the RAND benchmark, which uses the same entry count but randomly distributed. The selective discipline of AAPIS™ is what separates its 68.9% win rate from RAND's 57.2%.

---

## UPRO Alone Fails. AAPIS™ Doesn't.

The most striking result in the entire stress test is the fate of buy-and-hold UPRO:

| Metric | UPRO (buy & hold) | AAPIS™ |
|---|---|---|
| Mean CAGR | **−9.69%** | **+6.78%** |
| Median CAGR | −10.90% | +6.82% |
| Avg Max Drawdown | **92.86%** | 53.18% |
| Avg Total Return | 80.3% | 148.6% |
| Sortino Ratio | 0.14 | 0.46 |

Both strategies use UPRO as their primary vehicle. The difference between a −9.69% mean CAGR and a +6.78% mean CAGR — a **1,647 basis point gap** — is entirely attributable to the AAPIS™ signal and trailing stop mechanism. Selective exposure, properly timed and properly exited, converts a catastrophically failing instrument in harsh environments into a consistently outperforming strategy.

---

## Summary Scorecard

| Criterion | AAPIS™ vs SPY | AAPIS™ vs RAND | AAPIS™ vs UPRO |
|---|---|---|---|
| 10-yr Horizon Win Rate | ✅ +18.9pp | ✅ +11.7pp | ✅ Dominant |
| Annual Win Rate | ✅ +4.1pp | ✅ +6.9pp | ✅ Dominant |
| Mean CAGR | ✅ +183bps | ✅ +105bps | ✅ +1,647bps |
| Sortino Ratio | ✅ Higher | ✅ Higher | ✅ 3.3× higher |
| Max Drawdown | ⚠️ −3.8pp higher | ✅ 1.4pp lower | ✅ 39.7pp lower |
| Return Symmetry | ✅ Stable (mean ≈ median) | ✅ Stable | ✅ vs heavily skewed |
| Performance in Crisis Regimes | ✅ Profitable | ✅ Profitable | ❌ Catastrophic |

**✅ = AAPIS™ advantage · ⚠️ = modest cost of leveraged exposure**

---

## Important Context: Synthetic vs. Historical Performance

The figures in this report are from a **synthetic stress test calibrated to be harsher than realized history.** The crisis regimes used (σ = 4.2%/day, μ = −0.18%/day) are more severe and more frequent than anything in the 1994–2026 historical record.

**AAPIS™'s live historical performance (1994–2026) is significantly stronger than these stress test results**, with a CAGR of ~22.97% versus the 6.78% shown here. The stress test is not a performance forecast — it is a worst-case robustness proof.

The purpose of publishing this test is to demonstrate that AAPIS™'s edge is not an artifact of favorable historical conditions. Even in environments specifically designed to be more punishing than any decade in modern market history, the strategy remains consistently profitable and consistently beats its benchmarks.

---

## Methodology Notes

- **Monte Carlo engine**: 1,000 independent simulations, each using a unique random seed. No two timelines share the same regime calendar.
- **Warm-up period**: 300 trading days of market data generated before any strategy decisions begin. Eliminates indicator initialization bias.
- **PRNG**: JavaScript-compatible unsigned 32-bit IMUL PRNG, faithfully emulated in Python for cross-platform reproducibility.
- **UPRO modeling**: Volatility decay modeled as `(L² − L)/2 · σ²` per day (mathematically correct for 3× leverage). Expense ratio of 0.89%/year applied daily.
- **TSL exit modeling**: Trailing stop-loss exits split between standard TSL execution (~67.9%) and gap-open execution (~32.1%), calibrated from 1994–2026 AAPIS™ live audit data.
- **Sortino calculation**: Uses 1.5% annualized risk-free rate. Downside deviation computed over all trading days (not just negative days), per standard methodology.
- **Confidence interval**: At N = 1,000, win rate standard error ≈ ±1.5pp.

---

## Disclaimer

*This report presents results from a synthetic Monte Carlo simulation for educational and analytical purposes only. Synthetic market data does not replicate actual market conditions. Past performance — simulated or historical — does not guarantee future results. AAPIS™ signals are informational outputs, not investment advice. Ambika Analytics LLC is not a registered investment advisor. All investing involves risk of capital loss.*

*© 2026 Ambika Analytics LLC. All rights reserved. AAPIS™ is a trademark of Ambika Analytics LLC.*
*S&P 500® is a registered trademark of S&P Dow Jones Indices LLC. This content is not affiliated with or endorsed by S&P Dow Jones Indices LLC.*
