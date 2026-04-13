# Data Sources — Fisheries / Coral Monte Carlo Simulation

Channel parameters in `mc_simulation.py` trace to the sources listed here.
The paper (Fisheries / Coral: External Forcing Impossibility) is available on SSRN and contains the full
reference list and §4 calibration narrative.

---

## Channel Sources

### `C1_stock_depletion`

Foregone economic rent from overfishing beyond E_MSY. World Bank (2017) Arnason bioeconomic model: gap between actual ($3B/yr) and MEY ($86B/yr) profitability.

*Full citations: paper §4 (available SSRN).*

### `C2_bycatch_discards`

Lost commercial value of 38M tonnes bycatch/yr (WWF), premature fishery closures, reduced prey base. Excludes non-market existence values.

*Full citations: paper §4 (available SSRN).*

### `C3_benthic_habitat_destruction`

Bottom trawling habitat damage (Pristine Seas 2025: €11B/yr Europe, scaled globally) + conservative carbon externalities. Wide CI reflects Sala-Hiddink debate.

*Full citations: paper §4 (available SSRN).*

### `C4_iuu_fishing`

Ex-vessel value of IUU catch (Agnew et al. 2009: 11-26M tonnes, $10-23.5B). Theft from sovereign resources + organized crime nexus.

*Full citations: paper §4 (available SSRN).*

### `C5_capacity_enhancing_subsidies`

Direct fiscal transfer from Sumaila et al. (2019): $22.2B capacity-enhancing of $35.4B total. Excludes amplification effects (conservative).

*Full citations: paper §4 (available SSRN).*

### `C6_governance_forced_labor`

ILO forced labor valuation + RFMO governance failure cost (gap between recommended and adopted measures). Wide CI reflects measurement challenges.

*Full citations: paper §4 (available SSRN).*

---

## Industry Revenue (Π)

The private payoff Π = $38.0B/yr is global annual industry revenue.
Source: paper §2 and §4. See paper §DA-1 (Decision Audit Field 7) for full
revenue source documentation.

---

## SAPM Framework

- Postnieks, E. (2026). *The Private Pareto Theorem*. SAPM Foundation Paper. SSRN.
- Postnieks, E. (2026). *Fisheries / Coral (External Forcing Impossibility)*. SAPM Working Paper. SSRN.

---

## Distribution Methodology

- Iman, R. L., & Conover, W. J. (1982). A distribution-free approach to
  inducing rank correlation among input variables. *Communications in
  Statistics — Simulation and Computation*, 11(3), 311–334.
- Cooke, R. M. (1991). *Experts in Uncertainty*. Oxford University Press.
