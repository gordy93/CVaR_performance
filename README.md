# CVaR_performance
This notebook is a portfolio research framework comparing three optimization approaches:
- Mean-Variance (Markowitz, 1952).
- Mean-CVaR (Vorobets, 2022).
- Demeaned-CVaR (Vorobets, 2022).

The notebook uses Fortitudo's open-source implementation (`fortitudo.tech`) to demonstrate the methodology, run controlled simulations and evaluate portfolio implications across multiple market regimes.

Third-party dependency (GPL-3.0): this notebook imports `fortitudo.tech` (GPL-3.0). All notebook code, simulation design and analysis are unrelated to Fortitudo. The package is used strictly as a dependency to implement EP mechanics.

---

## Core ideas

1) Regime-based risk modeling
The notebook simulates returns across multiple market regimes, evaluating portfolio construction under multiple conditions.

2) Stress-view integration via entropy pooling
A key feature is the use of stress views, then updating scenario probabilities through Sequential Entropy Pooling (Vorobets, 2022). This shifts the distribution itself, not just portfolio weights.

3) Constraint-aware optimization
The study compares different implementation realities:
- long-only.
- long-only with allocation bounds.
- long-short with bounded exposures.
This shows how constraints can materially change portfolio shape and method behavior.

4) Confidence-driven posterior blending
The framework introduces confidence levels for posterior views:
- Fixed confidence sets for direct comparison.
- Dynamic confidence sweeps for sensitivity analysis.
Explaining how portfolio decisions change as conviction in posteriors change.

5) Portfolio simulation
Rather than just modelling efficient frontiers, the notebook performs a 5-year out-of-sample simulation with:
- Daily/weekly/monthly rebalancing.
- Turnover-based transaction costs.
- Bayesian updating of confidence.
- Benchmark comparison vs Mean-Variance vs Mean-CVaR vs Demeaned-CVaR.
Evaluating return, risk-adjusted performance, drawdowns and turnover to reflect realistic outcomes.

High-level conclusions
- CVaR-based methods generally act more conservatively than Mean-Variance.
- Portfolio constraints are a major driver of diversification and aggressiveness.
- Confidence in stress views strongly impacts allocations and performance.

## License / attribution

This notebook uses the `fortitudo.tech` package (GPL-3.0) as a third-party dependency.  
All notebook code in this repository are not related to Fortitudo; the package is only imported to illustrate its capabilities and its potential implementation.  
For the license terms, see the `fortitudo.tech` project’s GPL-3.0 license.
