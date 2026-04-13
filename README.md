# SAPM Monte Carlo — Fisheries / Coral / External Forcing Impossibility

**Public replication repository for quantitative results in:**

> Postnieks, E. (2026). *Fisheries / Coral (External Forcing Impossibility).* SAPM Working Paper. SSRN.

This repository provides everything needed to independently reproduce, audit,
and extend the Monte Carlo simulation underlying the paper's core results.
The paper is available on SSRN.

---

## Results (N = 100,000 draws, seed = 42)

| Statistic | Value |
|-----------|-------|
| **β_W median** | **4.7** |
| β_W mean | 4.73 |
| β_W std | 0.6 |
| **90% CI** | **[3.8, 5.8]** |
| 99% CI | [3.5, 6.3] |
| P(β_W < 1) | 0.0000% |
| **ΔW median** | **$178.6B/yr** |
| Π (revenue) | $38.0B/yr |

**β_W = 4.7** means the fisheries / coral industry destroys **$4.7 in system
welfare for every $1.00 in revenue** — across 6 channels and 100,000 Monte Carlo draws.

**Classification**: Class 1 — Impossibility

---

## What Is β_W?

```
β_W = ΔW / Π
```

- **ΔW** = total annualized welfare destruction ($B/yr) across all channels
- **Π** = annual industry **revenue** ($B/yr) — not profit

β_W > 1: industry destroys more welfare than it captures in revenue.
β_W > 3: Strong Intractability threshold — reform requires structural replacement.

---

## Quick Start

```bash
git clone https://github.com/epostnieks/sapm-mc-fisheries.git
cd sapm-mc-fisheries
pip install numpy scipy
python mc_simulation.py
```

Expected output: `β_W median : 4.7` and `ΔW median : $178.6B/yr`

---

## Welfare Channels

| Channel | Median ($B/yr) | 90% CI | Distribution |
|---------|---------------|--------|--------------|
| C1_stock_depletion | $82.9B | [$65.5B, $104.9B] | Lognormal |
| C2_bycatch_discards | $15.0B | [$10.0B, $20.0B] | Normal |
| C3_benthic_habitat_destruction | $27.0B | [$17.4B, $42.0B] | Lognormal |
| C4_iuu_fishing | $17.0B | [$10.0B, $24.0B] | Normal |
| C5_capacity_enhancing_subsidies | $22.2B | [$18.2B, $26.2B] | Normal |
| C6_governance_forced_labor | $13.2B | [$7.9B, $22.0B] | Lognormal |
| **Total ΔW** | **$178.6B** | **[$144.7B, $219.5B]** | Correlated (ρ=0.3) |

---

## Impossibility Floor

The floor β_W ≥ 2.6 cannot be breached by any policy while the
industry continues to operate. In 100,000 draws, only **0.0000%**
fall below this floor — confirming the structural constraint.

## Repository Contents

| File | Description |
|------|-------------|
| `mc_simulation.py` | Self-contained simulation — no private pipeline imports |
| `mc_results.json` | Pre-run results (100K draws, seed=42) — matches paper |
| `mc_histogram.json` | Binned β_W distribution (80 bins) for companion chart |
| `assumptions.md` | Every parameter: value, derivation, source |
| `data_sources.md` | Full citation list for all empirical inputs |

---

## Replication Notes

Results are seeded and deterministic. Tested with:
```
numpy==1.26.4  scipy==1.12.0  Python 3.11.9
```

The `median` and `ci_90` (to 1 decimal) match exactly across compatible versions.

---

## License

CC BY 4.0. Cite as:

> Postnieks, E. (2026). *SAPM Monte Carlo — Fisheries / Coral (External Forcing Impossibility)*.
> GitHub: epostnieks/sapm-mc-fisheries.
> https://github.com/epostnieks/sapm-mc-fisheries
