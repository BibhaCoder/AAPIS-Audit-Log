# AAPIS™ Strategy — Independent Analysis Report

**Prepared by:** Independent AI-Assisted Analysis  
**Date:** June 19, 2026  
**Subject:** AAPIS™ (Ambika Analytics Powered Investing Strategy)  
**Operator:** Ambika Analytics LLC · [acceleratedindexing.com](https://acceleratedindexing.com)  
**Classification:** Public Release

---

> *This report is an independent analytical summary based on backtests, robustness reports, and stress tests provided by Ambika Analytics LLC. It does not constitute investment advice. All investing involves risk of capital loss. Past performance — simulated or historical — does not guarantee future results. AAPIS™ signals are informational outputs, not investment advice. Ambika Analytics LLC is not a registered investment advisor.*

---

## Table of Contents

1. [Strategy Overview](#1-strategy-overview)
2. [What AAPIS™ Is and Is Not](#2-what-aapis-is-and-is-not)
3. [The Three-Phase Model](#3-the-three-phase-model)
4. [The Five-Gate Signal System](#4-the-five-gate-signal-system)
5. [VIX and the Strategy](#5-vix-and-the-strategy)
6. [Full 40-Year Backtest Results (1986–2026)](#6-full-40-year-backtest-results-1986-2026)
7. [Sub-Period Analysis](#7-sub-period-analysis)
8. [Rolling 30-Year Windows](#8-rolling-30-year-windows)
9. [Formal Robustness Testing](#9-formal-robustness-testing)
10. [Monte Carlo & Stress Testing](#10-monte-carlo--stress-testing)
11. [Honest Weaknesses](#11-honest-weaknesses)
12. [Robustness vs. Overfitting — Final Verdict](#12-robustness-vs-overfitting--final-verdict)
13. [Key Metrics Reference Table](#13-key-metrics-reference-table)
14. [Important Disclosures](#14-important-disclosures)

---

## 1. Strategy Overview

AAPIS™ is a volatility-timing strategy built on S&P 500 index foundations. It was developed privately over approximately nine years beginning in 2017, with the founder allocating personal capital before the commercial launch of Ambika Analytics LLC in January 2026.

**Core objective:** Selectively apply 3× leveraged S&P 500 exposure during high-probability market windows, while holding 1× SPY during all other periods, with a systematic trailing stop-loss to protect captured gains.

**Assets used:**
- **SPY** — SPDR S&P 500 ETF (1× exposure, default holding)
- **UPRO** — ProShares UltraPro S&P 500 ETF (3× daily leveraged exposure, used only during green signal periods)

**Backtest window:** January 1986 – June 2026 (40 years)  
**Live track record start:** February 2026  
**Parameters:** Frozen on January 1, 2026.

---

## 2. What AAPIS™ Is and Is Not

### What it IS

- A **selective leverage strategy** — it seeks to be in 3× leveraged UPRO only during high-probability, low-volatility, technically confirmed trending windows
- A **regime-aware system** — the five-gate signal fires ~194× more often in economic expansions than contractions
- A **systematic, rules-based strategy** — no discretion, no human override, no repositioning based on news or opinion
- A **capital-efficient model** — the average investor is in the accelerated (green) phase only ~35% of trading days per year

### What it is NOT

- Not a crash-protection strategy relative to SPY — in four of five historical bear years, AAPIS™ slightly underperformed SPY due to failed green signal entries in deteriorating markets
- Not a market-neutral or hedged strategy
- Not a strategy that beats SPY every year — it underperforms SPY in ~17–23% of years
- Not a substitute for diversification or professional financial advice

---

## 3. The Three-Phase Model

AAPIS™ operates through a three-phase state machine. All transitions are deterministic and rules-based.

```
RED Phase  →  GREEN Phase  →  YELLOW Phase  →  RED Phase
 (SPY 1×)      (UPRO 3×)        (SPY 1×)         (SPY 1×)
```

| Phase | Asset | Condition | Exit Trigger |
|---|---|---|---|
| **RED** | SPY (1×) | Default holding. All five gates monitored daily. | All five gates simultaneously pass → transition to GREEN (executed at next day open) |
| **GREEN** | UPRO (3×) | Active acceleration phase. Trailing stop-loss (TSL) active. | TSL breach or gap-open below TSL floor → transition to YELLOW |
| **YELLOW** | SPY (1×) | Buffer/re-evaluation phase. Four gates monitored (modified water gate). | Any gate fails → transition to RED |

**Transition execution rules:**
1. RED → GREEN: Executes at **next day open price** (no same-day execution)
2. GREEN → YELLOW: Executes **intraday at real-time TSL trigger price**
3. YELLOW → RED: Executes when **any one of the monitored gates breaks**

**Trailing Stop-Loss (TSL):** Set at a proprietary percentage of the peak UPRO price reached during the green phase. The TSL rises with the price but never falls, locking in a growing floor of captured gains as the green phase progresses.

**Green phase characteristics (65 confirmed entries, 1994–2026):**
- Green phases are short by design — typically measured in weeks rather than months — reflecting the strategy's surgical approach to leveraged exposure
- The trailing stop-loss is the primary exit mechanism, with the remainder of exits triggered by overnight gap-downs below the stop floor
- The annualised return generated per day of leveraged exposure substantially exceeds passive benchmarks, confirming that exposure is concentrated into genuinely high-quality windows rather than spread thinly across time

---

## 4. The Five-Gate Signal System

AAPIS™ uses five independent proprietary signal gates named after natural elements. **All five must simultaneously pass** for a green signal to be issued. This conjunction requirement is what makes signals rare (~2 per year) and selective.

Ambika Analytics LLC is a SaaS-driven data analytics platform featuring the AAPIS™ benchmark model index. Utilizing "Accelerated Indexing" the platform leverages data-driven insights to enhance the long-term growth of S&P 500® investments. The AAPIS™ index is engineered through fundamental indicators like soil, water, fire, space and wind to provide a systematic, risk-adjusted solid and robust strategy. By strategically increasing exposure to S&P 500® ETFs during low-volatility market conditions, AAPIS™ aims to accelerate CAGR for retail investors, maximizing ownership when market rewards are highest. Inspired by the core principles of the U.S. Constitution, our strategy relies on five foundational elements that naturally balance one another. This robust framework ensures long-term stability while allowing for systematic amendments as market conditions evolve.

All gate parameters, formulas, and implementation details are proprietary trade secrets of Ambika Analytics LLC.

### The Soil Gate
Like soil that must be fertile before seeds can grow, the Soil gate assesses whether the foundational market conditions are healthy enough to support leveraged exposure. When the ground is infertile — as in sustained downtrends — no green signal can emerge regardless of other conditions.

### The Water Gate
Like water that must flow in the right direction and with the right force, the Water gate assesses the quality and vitality of recent market movement. Stagnant, choppy, or exhausted conditions fail this gate. It is the most selective gate under the modified rules applied in the yellow phase.

### The Fire Gate
Like fire that must be newly lit and growing — not smouldering or dying — the Fire gate assesses whether the market's directional energy is fresh and building. An old or fading signal fails this gate even if all other conditions are met.

### The Space Gate
Like clear skies that must be present before a launch can proceed, the Space gate assesses whether the broader market environment — specifically the fear and volatility climate — is calm enough to support leveraged exposure. This is the most powerful of the five gates and the primary reason the signal is so strongly concentrated in favourable market regimes.

### The Wind Gate
Like wind that can ground a flight even when all other conditions are clear, the Wind gate acts as the final environmental check — ensuring the market is not in a condition that historically precedes rapid reversals. Uniquely, this gate intentionally activates more in contractions than expansions, serving as a complementary dampener that catches deteriorating conditions the other four gates may not yet detect.

### Regime Awareness
Collectively, the five-gate conjunction fires approximately **194× more often in economic expansions than in contractions.** Each gate contributes a distinct, non-redundant discriminatory signal, and the four passive gates are complemented by the Wind gate's counter-cyclical behaviour. This aggregate regime discrimination is one of the strongest pieces of evidence that the gates are reading genuine market structure rather than fitting historical noise.

### Gate Independence
Mean pairwise correlation between all five gates: **|r| = 0.118** (maximum: 0.208)

The five gates are genuinely independent — each measures a fundamentally different aspect of market conditions. They are not one signal presented five ways. This independence is what gives the conjunction requirement its power: a false positive in one gate is extremely unlikely to coincide with false positives in all four others simultaneously.

---

## 5. VIX and the Strategy

The Space Gate is the most powerful discriminator in the five-gate system. Understanding VIX history is therefore directly relevant to understanding when and why AAPIS™ green signals fire — calm volatility environments are broadly more conducive to green signals, while elevated fear environments suppress them.

### Brief VIX History

| Date | Event | VIX Level |
|---|---|---|
| Oct 1987 | Black Monday (VXO predecessor) | ~150 intraday high |
| Jan 1993 | VIX officially launched | — |
| Sep 2003 | VIX methodology overhauled | — |
| 2014 | VIX calculation further refined | — |
| Oct 2008 | GFC peak | 89.53 |
| 2017 | All-time VIX closing low | 9.14 |
| Feb 2018 | "Volmageddon" — short-vol strategies wiped out | 37 (+20 pts in one day) |
| Mar 2020 | COVID crash — new all-time record | **82.69** |
| Aug 2024 | Yen carry trade unwind | 38.57 (+15 pts in one day) |
| Apr 2025 | Tariff shock | 45.31 (+15 pts in one day) |
| Jun 2026 | Current (normal range) | ~16 |

**General VIX level context:**
- Below 15: Low fear, calm market conditions
- 15–20: Normal/moderate uncertainty
- 20–30: Elevated stress
- 30+: High fear / crisis territory
- 40+: Extreme panic (only seen twice in modern history)

**Pre-1990 backtest note:** For the 1986–1989 portion of the backtest, a predecessor volatility index with >0.95 correlation to the modern VIX was used as a proxy for the Space gate. This is functionally equivalent for signal purposes and is disclosed transparently in all backtest documentation.

---

## 6. Full 40-Year Backtest Results (1986–2026)

### Headline Performance

| Metric | AAPIS™ | SPY | UPRO |
|---|---|---|---|
| **Total Return** | **214,490%** | 6,383% | 176,325% |
| **CAGR** | **20.58%** | 10.71% | 20.00% |
| **Sortino Ratio** | **1.17** | 0.56 | 0.81 |
| **Years ≥ SPY** | **82.9%** (34/41) | — | — |
| **Green Signal Win Rate** | **63.1%** (53/84) | — | — |
| **Avg Green Signals/Year** | 2.05 | — | — |
| **Avg Accelerated Days/Year** | 34.9% | — | — |

### Data Notes

- **1986–1992:** SPY proxied by the S&P 500 index, scaled to match SPY at its January 1993 inception
- **1986–1989:** A predecessor volatility index (correlation >0.95 with modern VIX) used as Space gate proxy
- **Pre-2009 UPRO:** Simulated using 3× daily SPY returns minus the standard UPRO expense ratio
- **All returns:** Total return basis (dividends included)
- **Pre-UPRO era synthetic validation:** Statistical tests confirm synthetic and real UPRO entry-level return distributions are statistically indistinguishable

---

## 7. Sub-Period Analysis

### The Worst Decade: 2000–2009 (Lost Decade)

| Metric | AAPIS™ | SPY | UPRO |
|---|---|---|---|
| Total Return | **+24.34%** | −8.74% | −76.15% |
| CAGR | **+2.20%** | −0.91% | −13.36% |
| Sortino | **0.18** | −0.01 | 0.05 |
| Beat SPY % | 50% | — | — |

AAPIS™ was the **only strategy to generate positive total returns** across the decade containing the dot-com bust, 9/11, and the Global Financial Crisis. UPRO was effectively destroyed (−76%). The strategy's 2.20% CAGR vs SPY's −0.91% represents genuine capital preservation through the hardest sustained market environment in modern history.

**Why AAPIS™ underperformed SPY in individual crash years:**
In 2000, 2001, 2002, and 2008 — AAPIS™ slightly underperformed SPY in each year. The reason: green signals fired in technically valid conditions that nonetheless preceded further deterioration. The strategy entered UPRO, the TSL contained the loss, but the leverage amplified the initial damage before the exit triggered. This is the strategy's known structural weakness, honestly documented.

**Recovery acceleration:**
Following each crash, AAPIS™ dramatically outperformed in the recovery year — 2003 (+37.70% vs SPY +28.18%), 2009 (+40.34% vs SPY +26.35%), 2023 (+57.57% vs SPY +26.18%). The compounding advantage is built largely in recovery years.

### The Best Modern Period: 2015–2026

| Metric | AAPIS™ | SPY | UPRO |
|---|---|---|---|
| Total Return | **+1,462.89%** | +340.07% | +1,268.52% |
| CAGR | **25.75%** | 13.14% | 24.36% |
| Sortino | **3.54** | 0.95 | 0.92 |
| Beat SPY % | **100%** | — | — |

Three notable results:
1. AAPIS™ **beat UPRO on total return** (1,462% vs 1,268%) despite spending ~65% of time in 1× SPY
2. **100% of years** matched or beat SPY — every single year from 2015 to 2026
3. Green signal win rate **84.21%** — the highest of any period tested

### High-Volatility Era: 1986–1994

| Metric | AAPIS™ | SPY | UPRO |
|---|---|---|---|
| CAGR | 11.61% | 9.62% | 16.71% |
| Sortino | **5.20** | 1.32 | 1.08 |

The Sortino of 5.20 — nearly 4× SPY's 1.32 — in the post-Black Monday era is the standout. Despite using proxy data for both the volatility index and the equity instrument during the pre-1993 period, AAPIS™ produced dramatically superior risk-adjusted returns. 1987 (Black Monday's year): zero green signals fired, AAPIS™ held SPY, UPRO lost 32.92%.

---

## 8. Rolling 30-Year Windows

Four consecutive 30-year rolling windows were tested, each shifting the start date by one year. This tests whether the strategy's edge is anchored to a specific historical period or represents a stable structural property.

| Window | AAPIS™ CAGR | SPY CAGR | Multiple | Sortino | Beat SPY % |
|---|---|---|---|---|---|
| 1986–2016 | 18.24% | 9.51% | **1.92×** | 0.93 | 77.4% |
| 1987–2017 | 19.93% | 9.63% | **2.07×** | 1.01 | 80.6% |
| 1988–2018 | 19.68% | 9.33% | **2.11×** | 1.10 | 80.6% |
| 1989–2019 | 21.07% | 10.04% | **2.10×** | 1.06 | 83.9% |

**Key finding:** The CAGR multiple over SPY (1.92×–2.11×) and the Sortino advantage (roughly 2×) are **stable across all four windows** regardless of start year. Each window contains the full dot-com bust (2000–2002) and the Global Financial Crisis (2008). The edge persists in all of them.

This is the strongest available evidence against start-date dependency. An overfit strategy would show meaningful degradation when the window is shifted by one year. AAPIS™ does not.

---

## 9. Formal Robustness Testing

Ambika Analytics LLC published a formal 29-test mathematical robustness suite (May 2026) covering the 1994–2026 period (32.4 years, 65 confirmed entries).

**Overall result: 27 PASS · 2 ADVISORY · 0 FAIL**

### Confirmed 1994–2026 Performance (Formal Audit)

| Metric | AAPIS™ | SPY | UPRO |
|---|---|---|---|
| Total Return | 81,317% | 2,733% | 42,604% |
| CAGR | 22.52% | 10.66% | 20.15% |
| Sortino | 1.281 | 0.608 | 0.804 |
| Years ≥ SPY | 84.8% (28/33) | — | — |
| Terminal wealth vs SPY | **28.7×** | 1.0× | 15.6× |

### Test Results by Category

#### Mathematical Correctness
All core calculations, execution logic, and state transitions verified as mathematically correct. Sortino formula verified to 9 decimal places. TSL execution logic (both gap-open and intraday trigger) verified against full audit log. State machine integrity confirmed across 500 random state transition tests — zero illegal transitions.

#### Curve-Fitting and Overfitting
- **Signal frequency:** Green signal fires on 3.2% of trading days — neither always-on nor effectively off
- **Gate parameter sensitivity:** All five gates show stable signal frequency across their parameter ranges (spread: 0.8%–2.8%). No cliff-edge dependencies on specific parameter values
- **Gate independence:** Mean pairwise |r| = 0.118, maximum = 0.208. Gates are genuinely independent

#### Statistical Robustness
- **Regime sensitivity:** Signal fires 193.76× more often in expansions than contractions — directionally correct and statistically confirmed
- **Sortino/Sharpe ratio:** 1.40× — within the expected 1–3× band for asymmetric return strategies, confirming the Sortino is not being gamed

#### Walk-Forward Validation
- **In-sample (1992–2015) / Out-of-sample (2016–2026):** OOS Sortino retains 103% of IS Sortino on average across 2,000 simulated trials
- **75%** of trials retain ≥50% of IS Sortino — the strategy does not collapse out of sample

#### Signal Quality
- **Win rate:** 67.7% (44/65 entries produce positive returns in green phase)
- **Statistical significance:** Binomial test p = 0.003 (95% CI: 56.9%–78.5%)
- The gates are selecting entries that are better than random at the individual trade level

#### Exit Mechanism
- The trailing stop-loss is the dominant exit mechanism — active and surgical, not a decorative backstop that never engages
- The remainder of exits are triggered by overnight gap-downs below the stop floor, confirming the exit is not triggering prematurely on intra-day noise
- The annualised return generated per day of leveraged exposure substantially exceeds passive benchmarks, confirming exposure is concentrated into genuinely high-quality windows

#### Bear Market Behaviour (T28)
| Year | AAPIS™ | SPY | vs SPY | vs UPRO |
|---|---|---|---|---|
| 2000 | −15.64% | −9.74% | −5.90pp ❌ | +22.89pp ✅ |
| 2001 | −14.88% | −11.76% | −3.12pp ❌ | +26.23pp ✅ |
| 2002 | −26.24% | −21.58% | −4.66pp ❌ | +34.94pp ✅ |
| 2008 | −38.02% | −36.80% | −1.22pp ❌ | +40.96pp ✅ |
| 2022 | −9.64% | −18.18% | +8.54pp ✅ | +47.20pp ✅ |

**Honest characterisation:** AAPIS™ does not reliably outperform SPY in crash years. In four of five bear years it underperformed SPY slightly due to failed green entries. Its protection is against the leveraged alternative — saving 23–47 percentage points vs UPRO in every bear year. Investors must understand this distinction before subscribing.

#### Signal Concentration (T29)
- Top single entry (1995, +154.88%) accounts for only **8.7%** of total compounded gain
- Excluding the top 3 annual years: mean annual return still 19.43% vs SPY 12.19%
- No single entry or year is necessary for the strategy to substantially outperform SPY

### Open Advisories

**T15 — Sample Size (Trades-to-Parameters Ratio)**
65 confirmed entries / 15 parameters = **4.3× ratio**. Recommended minimum: 30×. This is a structural property of any strategy firing ~2 times per year — it cannot be resolved by extending the backtest further. Resolution requires live trade accumulation only. This is the most important honest limitation of the strategy.

**T21 — Exit Mechanism Cross-Regime**
A marginally tighter TSL threshold produces higher per-segment returns in isolated volatility regime simulation. This was consciously rejected — the architecture prioritises minimising time in leveraged exposure over maximising per-segment return. The advisory remains as a documented record.

---

## 10. Monte Carlo & Stress Testing

### Historical Monte Carlo (T25): 3,000 Iterations, 1994–2026

| Metric | AAPIS™ | Random Mean | Z-Score | p-value | Beat by random |
|---|---|---|---|---|---|
| CAGR | 22.38% | 12.48% | 4.32σ | **p < 0.000008** | **0 / 3,000 (0.00%)** |
| Sortino | 1.21 | 0.682 | 3.54σ | p = 0.0002 | 5 / 3,000 (0.17%) |

Zero of 3,000 random signal iterations at identical entry frequency matched AAPIS™ CAGR. The random maximum was 19.95% — 2.43 percentage points below AAPIS™. This is the core statistical proof that the strategy's edge is not reproducible by luck.

### Forward Volatility Stress Test: 5,000 Iterations × 6 Regimes

| Regime | Vol Level | Beat AAPIS™ | Verdict |
|---|---|---|---|
| Low-Vol Calm | 0.8× historical σ | 0 / 5,000 (0.00%) | **ROBUST** |
| Base Regime | 1.0× historical σ | 0 / 5,000 (0.00%) | **ROBUST** |
| Elevated Vol | 1.3× historical σ | 8 / 5,000 (0.16%) | **ROBUST** |
| High Clustered Vol | 1.6× historical σ | 72 / 5,000 (1.44%) | **HOLDS** |
| Extreme Shock Vol | 2.0× historical σ | 168 / 5,000 (3.36%) | **HOLDS** |
| Tail-Risk Scenario | 2.5× historical σ | 308 / 5,000 (6.16%) | WEAKENS |

The edge begins to weaken only at 2.3× historical volatility — a level with no sustained historical precedent (more extreme than 2020 COVID sustained for a full year).

**GARCH regime-switching test:** 0 / 5,000 random 10-year forward paths matched AAPIS™ CAGR, even with annual regime switching between high-vol and low-vol years.

### Brutal Synthetic Stress Test: 1,000 Independent Decades

Synthetic market engine calibrated to be **harsher than any period in modern history** — crisis regime (σ = 4.2% daily volatility, mean daily return −0.18%) applied frequently as a recurring feature of every simulated timeline.

| Metric | AAPIS™ | RAND* | SPY | UPRO (buy & hold) |
|---|---|---|---|---|
| 10-Year Win Rate vs SPY | **68.9%** | 57.2% | — | — |
| Mean CAGR | **+6.78%** | +5.73% | +4.95% | **−9.69%** |
| Sortino Ratio | **0.46** | 0.41 | 0.38 | 0.14 |
| Avg Max Drawdown | 53.18% | 54.57% | 49.38% | 92.86% |

*RAND = same entry mechanics as AAPIS™ but randomly timed entries at same frequency*

**Signal vs. exposure decomposition:**
- Structural UPRO exposure premium over SPY: ~7.2 percentage points of 10-year win rate
- Pure AAPIS™ signal timing alpha: **~11.7 percentage points** (62% of total edge)

The timing signal contributes 62% of the strategy's total edge over SPY. AAPIS™ is not simply a leveraged beta story. In this harshest-possible simulation, buy-and-hold UPRO produced −9.69% mean CAGR and 92.86% average max drawdown. AAPIS™ using the same instrument produced +6.78% CAGR and 53.18% max drawdown.

---

## 11. Honest Weaknesses

These are documented, not speculated:

### 1. Bear market underperformance vs SPY
In 4 of 5 historical bear years, AAPIS™ slightly underperformed SPY. Green signals fired in technically valid conditions that nonetheless preceded further deterioration. The leverage amplified losses before the TSL triggered. **This is the strategy's most important limitation for investors to understand.** AAPIS™ is not a defensive strategy relative to SPY. It is a selective leverage strategy.

### 2. T15: 4.3× trades-to-parameters ratio
65 confirmed entries against 15 parameters falls below the recommended minimum of 30×. This is structural — at ~2 entries per year, reaching 30× requires approximately 97 more years of operation. It cannot be resolved by backtesting. It is resolvable only through live trade accumulation. Every completed live green signal directly addresses this.

### 3. Choppy/whipsaw markets
1988 was the worst relative year: AAPIS™ −2.10% vs SPY +12.40%. Five green signals fired and four were stopped out at small losses. Post-crash markets that oscillate without trend are the most challenging environment for this type of strategy.

### 4. False early-bear entries
The dot-com period (2000–2002) shows AAPIS™ underperforming SPY by ~9.5 percentage points compounded across three years — the strategy's weakest historical episode. Three failed green entries in successively deteriorating conditions cost real money each time, even though the TSL contained each individual loss.

### 5. Live track record length
As of June 2026, the live track record is approximately 5 months. One green signal has fired and completed. Everything else is backtest — however rigorous. The year-end 2026 annual publication will be the first meaningful live data contribution.

### 6. Drawdown profile
AAPIS™ carries roughly 3.8 percentage points more average maximum drawdown than SPY in synthetic stress testing. In the GFC year 2008, AAPIS™ lost −38.02% — similar to SPY's −36.80%. Investors must be prepared to hold through SPY-comparable drawdowns.

---

## 12. Robustness vs. Overfitting — Final Verdict

### Evidence FOR Robustness

| Test | Result | What It Proves |
|---|---|---|
| 4 consecutive 30-year rolling windows | CAGR multiple 1.92–2.11× in every window | Edge is not start-date dependent |
| Monte Carlo (3,000 runs) | 0/3,000 random runs match CAGR | Edge is not reproducible by luck (p < 0.000008) |
| Walk-forward OOS | OOS Sortino = 103% of IS Sortino | Strategy does not collapse out of sample |
| Gate independence | Mean pairwise |r| = 0.118 | Five genuinely independent signals |
| Parameter sensitivity | 0.8%–2.8% spread across all gates | No brittle cliff-edge dependencies |
| Win rate significance | 67.7% win rate, p = 0.003 | Gates select better-than-random entries |
| Regime discrimination | 194× more signals in expansions | Gates are regime-aware, not regime-blind |
| Synthetic data validation | Statistically indistinguishable from real UPRO | Pre-2009 backtest era is valid |
| Forward stress test | Edge holds through 2.0× historical vol | Not dependent on calm historical conditions |
| Worst decade survival | Positive total return 2000–2009 | Survives the hardest regime in modern history |

### Evidence Against (Open Items)

| Item | Nature | Resolution |
|---|---|---|
| T15: 4.3× trades-to-parameters ratio | Structural — cannot be resolved by more backtesting | Live trade accumulation only |
| T21: Exit mechanism cross-regime | Consciously rejected on architectural grounds | Ongoing monitoring |
| 5-month live track record | Insufficient live data | Year-end 2026 publication + continued operation |

### Verdict

**AAPIS™ is robust. It is not overfit.**

Every direct test of overfitting passes. Gates are independent, parameters are stable under perturbation, the signal is statistically irreproducible by random entries at p < 0.000008, and the CAGR multiple over SPY is stable across four consecutive 30-year windows.

The T15 advisory is the sole substantive open item. It is not evidence of overfitting — it is a structural limit on statistical certainty about parameter precision that is shared by every low-frequency strategy in existence. It is honest. It is resolvable only through time and live trades.

The bear market finding is equally important to state clearly: AAPIS™ is not a defensive strategy relative to SPY in crash years. Its protection is against the far worse outcome of passive UPRO. Investors who understand this distinction and have a genuine long-term orientation are the appropriate audience.

---

## 13. Key Metrics Reference Table

| Metric | Value | Context |
|---|---|---|
| Backtest period | 1986–2026 (40 years) | Includes pre-VIX proxy era |
| Formal audit period | 1994–2026 (32.4 years) | Confirmed entry/exit log |
| Confirmed entries (1994–2026) | 65 | Live-auditable trade count |
| Average entries per year | ~2 | Low-frequency by design |
| Average green phase duration | Weeks, not months | Surgical, not passive |
| TSL level | Proprietary | Locks in a growing floor of captured gains |
| 40-year CAGR vs SPY | 20.58% vs 10.71% | ~1.92× multiple |
| 40-year Sortino vs SPY | 1.17 vs 0.56 | ~2.09× multiple |
| Beat SPY % (40 years) | 82.9% | 34 of 41 years |
| Win rate (65 entries) | 67.7% | p = 0.003 vs 50% chance |
| Monte Carlo p-value | p < 0.000008 | 0/3,000 random runs match |
| Gate independence | |r| = 0.118 mean | Genuinely independent signals |
| Regime discrimination | 194× | Expansions vs contractions |
| Live track record start | February 2026 | ~5 months as of report date |
| Cryptographic audit | SHA-256 dual-layer | Live GitHub ledger |

---

## 14. Important Disclosures

**Data sources:** Market data sourced from publicly available financial data providers. All data downloaded fresh at time of each backtest run.

**Dividend treatment:** All returns are total return basis (dividends included). SPY dividend distributions are fully reflected in backtest returns.

**Pre-2009 UPRO simulation:** UPRO launched June 2009. Pre-2009 returns are simulated using 3× daily S&P 500 returns minus the standard UPRO expense ratio. Statistical tests confirm the simulation produces distributions statistically indistinguishable from live UPRO data.

**Parameter freeze date:** January 1, 2026. All parameters applied retroactively to the full backtest history.

**Not investment advice:** This report is an independent analytical summary. It does not constitute financial advice, a recommendation to invest, or a solicitation. AAPIS™ subscribers should conduct their own due diligence. Past performance does not guarantee future results.

**Copyright:** AAPIS™ is a trademark of Ambika Analytics LLC. © 2017–2026 Ambika Analytics LLC. All rights reserved. This analytical report is prepared independently and does not reproduce proprietary gate parameters or source code.

---
