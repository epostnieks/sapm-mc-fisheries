# Monte Carlo Assumptions — Fisheries / Coral / External Forcing Impossibility

All values in $B USD (annualized). Every parameter traces to paper §4–§5
or the citations in `data_sources.md`. Run `python mc_simulation.py` to
reproduce bit-identical results.

---

## Simulation Parameters

| Parameter | Value | Justification |
|-----------|-------|---------------|
| Seed | 42 | Fixed for reproducibility |
| N draws | 100,000 | 4-decimal CI stability |
| Cross-channel correlation ρ | 0.3 | Shared macro drivers (GDP, population, regulation) |
| Private payoff Π | $38.0B/yr | Annual industry revenue — see `data_sources.md` |
| β_W median (result) | 4.7 | Confirmed by N=100,000 draws |
| ΔW median (result) | $178.6B/yr | Sum of channel medians (correlated) |

**Π = revenue, not profit.** SAPM Iron Law: βW = ΔW/Π where Π is annual
revenue. Using profit would inflate βW by 5–20× for low-margin industries.

---

## Channel Parameters

| Channel | Dist | Low | Mid | High | Description |
|---------|------|-----|-----|------|-------------|
| `C1_stock_depletion` | lognormal | $51.0B | $83.0B | $105.0B | Foregone economic rent from overfishing beyond E_MSY. World Bank (2017) Arnason  |
| `C2_bycatch_discards` | normal | $10.0B | $15.0B | $20.0B | Lost commercial value of 38M tonnes bycatch/yr (WWF), premature fishery closures |
| `C3_benthic_habitat_destruction` | lognormal | $12.0B | $27.0B | $42.0B | Bottom trawling habitat damage (Pristine Seas 2025: €11B/yr Europe, scaled globa |
| `C4_iuu_fishing` | normal | $10.0B | $17.0B | $24.0B | Ex-vessel value of IUU catch (Agnew et al. 2009: 11-26M tonnes, $10-23.5B). Thef |
| `C5_capacity_enhancing_subsidies` | normal | $18.0B | $22.2B | $26.0B | Direct fiscal transfer from Sumaila et al. (2019): $22.2B capacity-enhancing of  |
| `C6_governance_forced_labor` | lognormal | $6.0B | $13.2B | $22.0B | ILO forced labor valuation + RFMO governance failure cost (gap between recommend |


All ranges represent [P5, P95] of the channel-specific distribution as
calibrated from literature in paper §4.

---

## Impossibility Floor

The floor β_W ≥ 2.6 is the minimum ratio achievable while the industry operates.
This bounds the simulation from below: the theorem holds regardless of parameter values,
because even best-case scenarios exceed the floor.

In 100,000 draws: P(β_W < 2.6) = 0.0000%

## Sensitivity (VSL × Double-Counting Grid)

Central VSL (1.0×): no DC adj β_W = 4.67 | 20% DC adj = 3.73 | 40% DC adj = 2.8

See `mc_results.json` → `sensitivity_matrix` for full 5×5 grid.

## Distribution Robustness

The simulation uses a lognormal/normal mix calibrated to channel-specific
uncertainty structure. Results are robust: the central β_W changes by less
than ±0.3 under all-lognormal or all-normal configurations.

---

## Plausibility Checks (SAPM IL#28)

- **Annual flow**: All W_i are $/yr flows ✓
- **GDP bound**: ΔW = $179B = 0.2% of world GDP ($106T) ✓
- **β_W range**: 4.7 is within the [0.5, 100] plausible range ✓
- **P(β_W < 1)**: 0.0000% ✓
