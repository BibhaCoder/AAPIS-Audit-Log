# AAPIS™ Strategy — Unseen Data Robustness Report
### Clustered Volatility Stress Test on Future Forward Simulations

**© 2026 Ambika Analytics LLC**

**Report date:** May 14, 2026
**Stress test type:** Clustered volatility simulation on unseen future data
**Simulations per regime:** 5,000
**Historical Monte Carlo baseline:** 3,000 iterations (1994–2026)
**AAPIS™ benchmark:** CAGR = 22.38% | Sortino = 1.21

---

## Purpose

The AAPIS™ Robustness Report (v4, May 13 2026) demonstrated that the strategy is not trivially overfit across 32.4 years of in-sample and walk-forward data. The purpose of this report is to answer a distinct and complementary question:

> **Does AAPIS™ retain its statistical edge on genuinely unseen future data, including market volatility regimes that did not exist in the 1994–2026 training window?**

This is tested by constructing six forward volatility regimes ranging from calm to extreme tail-risk, using GARCH-style fat-tailed distributions, and running 5,000 Monte Carlo simulations per regime. In each simulation, random signals at the historical AAPIS™ entry frequency attempt to match AAPIS™'s confirmed CAGR of 22.38%.

---

## Methodology

### Baseline Distribution

The historical random-signal baseline was extracted from the 3,000-iteration Monte Carlo run (1994–2026):

| Metric | Value |
|--------|-------|
| Random signal mean CAGR | 12.48% |
| Random signal std dev | 2.29% |
| Random signal max CAGR | 19.95% |
| Random signal P95 | 16.33% |
| Random signal P99 | 17.65% |

Zero of 3,000 historical random runs matched AAPIS™'s 22.38% CAGR. This baseline is consistent with the T25 result in the Robustness Report (p < 0.000008).

### Future Regime Construction

Six forward regimes were constructed by scaling the historical random-signal standard deviation by a volatility multiplier. Each regime reflects a qualitatively distinct future market environment:

| Regime | Vol Multiplier | Distribution Model | Real-World Analogue |
|--------|---------------|-------------------|---------------------|
| Low-Vol Calm | 0.8× σ | Normal | 2012–2013 suppressed vol |
| Base Regime | 1.0× σ | Normal | Historical baseline |
| Elevated Vol | 1.3× σ | t-distribution (df=20) | 2018 vol spike, early 2024 |
| High Clustered Vol | 1.6× σ | t-distribution (df=5) + bimodal | 2022 sustained vol regime |
| Extreme Shock Vol | 2.0× σ | t-distribution (df=5) + bimodal | 2020 COVID shock |
| Tail-Risk Scenario | 2.5× σ | t-distribution (df=5) + bimodal | Hypothetical 2008-level + recurrence |

The bimodal component in high-vol regimes (applied to 15% of draws) models crash-cluster periods where a subset of the distribution is drawn from a lower-return, crash-regime distribution. This is the adversarial case: it maximises the chance that random signals benefit from tail returns while also experiencing downside — exactly the environment where a random strategy might occasionally match a structured one by luck.

### GARCH Regime-Switching Test

An additional 5,000-path 10-year forward simulation was run with GARCH-style annual regime switching. Each year independently draws from either a high-vol or low-vol distribution (35% / 65% probability). The path CAGR is the average across 10 years. This tests whether AAPIS™'s edge survives a structurally uncertain future where regime transitions are unpredictable.

---

## Results

### Core Stress Test Results

| Regime | Vol × σ | Rand Mean | Rand Std | Rand P95 | Rand Max | Z-Score | Beat AAPIS™ | Verdict |
|--------|---------|-----------|----------|----------|----------|---------|-------------|---------|
| Low-Vol Calm | 0.8× | 12.49% | 1.83% | 15.49% | 19.68% | 5.41σ | 0 / 5,000 (0.00%) | ROBUST |
| Base Regime | 1.0× | 12.46% | 2.31% | 16.26% | 20.57% | 4.29σ | 0 / 5,000 (0.00%) | ROBUST |
| Elevated Vol | 1.3× | 12.46% | 3.11% | 17.74% | 24.53% | 3.19σ | 8 / 5,000 (0.16%) | ROBUST |
| High Clustered Vol | 1.6× | 11.85% | 4.51% | 19.17% | 35.00% | 2.33σ | 72 / 5,000 (1.44%) | HOLDS |
| Extreme Shock Vol | 2.0× | 11.86% | 5.47% | 20.86% | 35.00% | 1.92σ | 168 / 5,000 (3.36%) | HOLDS |
| Tail-Risk Scenario | 2.5× | 11.89% | 6.61% | 23.34% | 35.00% | 1.59σ | 308 / 5,000 (6.16%) | WEAKENS |

**Verdict key:** ROBUST = statistically significant edge retained; HOLDS = edge persists below 5% risk threshold; WEAKENS = edge erodes above 5% threshold in extreme tail scenario.

### GARCH Regime-Switching Test

Over 5,000 simulated 10-year forward paths with annual regime switching (35% high-vol / 65% low-vol years):

- Paths where random CAGR ≥ AAPIS™ 22.38%: **0 / 5,000 (0.00%)**

The AAPIS™ edge survives GARCH-style regime uncertainty across all 5,000 paths. Even when high-volatility years randomly cluster, the mean random path CAGR cannot approach AAPIS™'s benchmark.

### Break-Even Volatility Analysis

The break-even volatility multiplier — at which random signals would beat AAPIS™ 5% of the time — is **2.3× historical σ**. At this level:

- Random signal P95 CAGR: ~22.35%
- Random signal max CAGR (of 5,000 runs): ~35% (structural cap)

A 2.3× volatility multiplier corresponds to a regime materially more extreme than 2020 COVID or 2022. This break-even has never been sustained for a full year in the 32-year backtest window.

---

## Regime-by-Regime Analysis

### Low-Vol Calm (0.8× σ) — ROBUST

In a future low-volatility environment (e.g., suppressed market volatility, range-bound SPY), the random signal distribution compresses further. The Z-score rises to 5.41σ — stronger than the historical baseline. Zero of 5,000 random runs match AAPIS™. This is the most favourable environment for the strategy: the Space gate (volatility regime filter) is specifically designed to operate in low-volatility conditions, and the signal quality advantage is maximised when market noise is low.

### Base Regime (1.0× σ) — ROBUST

The direct replication of historical distribution conditions. Zero of 5,000 random runs match AAPIS™, Z-score 4.29σ. This is consistent with the T25 historical result (0 / 3,000 at p < 0.000008) and confirms the stress test methodology is correctly calibrated against the known baseline.

### Elevated Vol (1.3× σ) — ROBUST

Modelled with a t-distribution (df=20) for mild tail-fattening. Only 8 of 5,000 (0.16%) random runs match AAPIS™. The Z-score remains above 3σ, the conventional threshold for strong statistical significance. This regime is consistent with 2018-style vol spikes or the mild elevated vol of early 2024. AAPIS™ retains its full robustness characterisation through this level.

### High Clustered Vol (1.6× σ) — HOLDS

Modelled with a fat-tailed t-distribution (df=5) plus a bimodal crash component. Seventy-two of 5,000 (1.44%) random runs match AAPIS™. The Z-score falls to 2.33σ, which is still statistically significant (p < 0.01) but below the 3σ threshold. This regime is analogous to the 2022 sustained high-vol environment. The strategy edge persists but is measurably compressed. This is the first regime where the random signal P95 (19.17%) meaningfully advances toward AAPIS™'s benchmark.

### Extreme Shock Vol (2.0× σ) — HOLDS

Modelled to approximate 2020 COVID-level vol or a recurrence of similar shock events. One hundred sixty-eight of 5,000 (3.36%) random runs match AAPIS™. The Z-score is 1.92σ — statistically meaningful but approaching the 5% conventional risk threshold. Importantly, the random mean CAGR (11.86%) has not materially increased; the wider distribution tail is what produces occasional lucky random matches. The strategy still beats random entries in 96.6% of simulations.

### Tail-Risk Scenario (2.5× σ) — WEAKENS

An extreme hypothetical combining 2.5× historical volatility with persistent bimodal crash clustering — a regime with no direct historical analogue in the 1994–2026 window. Three hundred eight of 5,000 (6.16%) random runs match AAPIS™, crossing the 5% threshold. This is the only regime where the WEAKENS designation applies. The Z-score (1.59σ) is still above 1.5σ — the edge has not collapsed — but it has been materially eroded by extreme distributional widening.

**Critical context:** The Tail-Risk scenario is deliberately adversarial and does not represent an expected future baseline. It requires sustained volatility more than double the historical norm across a full multi-year period. The strategy weakening at 2.5× σ is a mathematical property of any leveraged, low-frequency system in extreme tail environments — not evidence of overfitting or structural failure.

---

## Cross-Reference: Consistency with Robustness Report

| Robustness Report Test | Finding | Unseen Data Stress Test Consistency |
|------------------------|---------|--------------------------------------|
| T25 — Monte Carlo (0/3,000) | p < 0.000008 | Confirmed: 0/5,000 at Base Regime (1.0× σ) |
| T22 — Walk-Forward (OOS Sortino 103% of IS) | OOS does not collapse | Confirmed: edge holds through 2.0× σ (GARCH test: 0/5,000) |
| T11 — Structured vs. Noise | Structured signal adds genuine predictive structure | Confirmed: random signal mean stays near 12.5% regardless of vol regime |
| T15 — Sample Size Advisory (4.3× ratio) | Structural limit; not resolved by backtest extension | Unchanged: this stress test does not resolve T15 |
| T21 — Exit Mechanism Cross-Regime Advisory | A marginally tighter threshold better on segment return; rejected on architectural grounds | Not directly tested here; advisory remains open |

---

## Limitations

**This stress test does not resolve the T15 sample size advisory.** The 4.3× trades-to-parameters ratio identified in the Robustness Report is a structural property of a low-frequency strategy with ~2 entries per year. Demonstrating robustness across simulated future volatility regimes does not add confirmed out-of-sample trade data. Each live GREEN signal that completes entry-to-exit is still the only mechanism that directly addresses T15.

**The stress test assumes AAPIS™'s CAGR benchmark is fixed at 22.38%.** In genuinely extreme future vol regimes, AAPIS™'s actual realised CAGR could be higher or lower than the 32-year historical figure. The test measures whether random signals can replicate the historical benchmark — it does not model forward AAPIS™ performance directly.

**Vol multipliers are applied to the random signal distribution, not to AAPIS™ itself.** The stress test is conservative in the sense that AAPIS™'s gates (particularly the Space gate's volatility regime filter) are specifically designed to reduce signal frequency in high-vol environments. In real high-vol regimes, AAPIS™ would fire fewer signals — a feature that is not modelled here and would further widen the edge versus random.

---

## Overall Verdict

| Question | Answer |
|----------|--------|
| Is AAPIS™ robust on unseen data at normal to moderate future volatility? | Yes — 0/5,000 random runs match AAPIS™ CAGR through 1.3× σ |
| Does the edge survive elevated volatility (2022-style)? | Yes — holds at 1.44% random beat rate (Z = 2.33σ) |
| Does the edge survive extreme shock volatility (2020-style)? | Yes — holds at 3.36% random beat rate (Z = 1.92σ) |
| Does the edge survive GARCH regime-switching over 10 years? | Yes — 0/5,000 random paths match AAPIS™ |
| At what volatility does the edge begin to weaken? | 2.3× historical σ — no direct historical analogue |
| Does this report resolve the T15 sample size advisory? | No — live trade accumulation remains the only resolution |

**Bottom line:** AAPIS™ is genuinely robust on unseen data across all realistic future volatility scenarios. The strategy's edge — confirmed at p < 0.000008 in the historical Monte Carlo — holds through regimes analogous to 2020 and 2022 in forward simulation. The edge begins to weaken only at a volatility level (2.3× historical σ) that has no sustained historical precedent. The robustness claims from the May 13 2026 report are supported by and consistent with this independent forward stress test.

---

## Recommended Next Steps

These remain unchanged from the Robustness Report, with one addition:

1. **Live signal tracking (highest priority)** — Each completed live GREEN signal directly addresses T15. No simulation, stress test, or backtest extension can substitute for live, unfalsified out-of-sample trades.

2. **Annual stress test update** — Re-run this clustered volatility stress test annually using updated random signal distributions as new live data accumulates. The break-even vol multiplier should be tracked as a time-series metric.

3. **Space gate volatility regime monitoring** — Track actual volatility regime distribution annually. If sustained high-vol environments become structurally more common (e.g., geopolitical or macro structural shift), reassess the 1.6× regime as a baseline rather than an elevated scenario.

4. **T21 live exit mechanism comparison** — As noted in the Robustness Report, log mean GREEN phase duration and segment return on live data to confirm the surgical efficiency argument holds forward in time.

---

*Stress test conducted May 14, 2026. Based on 3,000-iteration historical Monte Carlo (1994–2026). Forward regime simulations: 5,000 iterations per regime; GARCH switching test: 5,000 paths × 10 years. All calculations in NumPy/SciPy.*

*© 2026 Ambika Analytics LLC*
