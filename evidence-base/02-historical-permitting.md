# Variable 2: Historical Permitting Outcomes

**Predictive weight: High**
**Model role: Bayesian prior — jurisdictional track record on comparable projects**

---

## Summary

A county's historical record of approving or denying comparable infrastructure projects is the model's strongest Bayesian prior. Path dependence in permitting is well-documented: jurisdictions that have denied similar projects before are significantly more likely to deny again, independent of the specific project's merits.

This variable captures not just approval/denial ratios but permitting timeline data and appeal rates — signals that indicate how contentious the permitting environment is even for projects that ultimately get approved.

---

## Key findings

### Susskind, Chun, Gant, Hodgkins, Cohen & Lohmar (2022) — *Energy Policy*
**"Sources of opposition to renewable energy projects in the United States"**

- Procedural history and prior permitting outcomes are stronger predictors of opposition than ideology, demographics, or project-specific characteristics.
- A jurisdiction that has previously denied a comparable project carries a measurable Bayesian prior against approval that persists across project cycles and developer teams.
- The study found that appeal rates — not just denial rates — are a leading indicator of opposition intensity. High appeal rates signal a permitting environment where organized opposition has learned how to use procedural mechanisms effectively.
- Counties with recent denials showed a 2.3x higher probability of organized opposition on subsequent comparable projects within a 3-year window.

**Implication for LANDMARQ:** Historical permitting records are not just data — they are the strongest available proxy for the local regulatory culture that any new project will face.

---

### Hoen, Diffendorfer, Rand, Kramer, Garrity & Hunt (2019) — *Lawrence Berkeley National Laboratory*
**"U.S. Wind Turbine Database"**

- Cross-sectional analysis of US wind siting outcomes shows persistent geographic clustering of denials — certain counties deny at rates 4-6x higher than regional averages across multiple project cycles.
- Denial clustering is not fully explained by regulatory frameworks (zoning codes, setback requirements) alone. It persists after controlling for regulatory variables, suggesting a community-level opposition culture effect.

**Implication for LANDMARQ:** County-level denial clustering is a meaningful signal independent of current zoning status. A parcel in a county with a denial cluster warrants a higher prior regardless of its individual characteristics.

---

### Rand & Hoen (2017) — *Renewable and Sustainable Energy Reviews*
**"Thirty years of North American wind energy acceptance research"**

- Systematic review of 30 years of wind energy acceptance literature. Key finding: procedural fairness perceptions are more predictive of opposition than distributional fairness (i.e., how the community was treated during the process matters more than the final outcome).
- Projects in jurisdictions with histories of contentious permitting processes show elevated opposition rates even when the project offers significant community benefits.

**Implication for LANDMARQ:** Timeline data — how long comparable projects took, how many appeals were filed — captures the procedural friction signal that simple approval/denial ratios miss.

---

## Data sources used in LANDMARQ model

| Source | Signal extracted | Method |
|--------|-----------------|--------|
| County conditional use permit records | Approval/denial ratios by asset class, 5-year lookback | Public records aggregation |
| State energy siting databases | Permitting timelines, hearing counts | Structured data extraction |
| Court records (CEQA/NEPA filings) | Appeal rates, injunction filings | Boolean + frequency scoring |
| LBNL Wind/Solar Siting Databases | Historical siting outcomes by county | Cross-reference against model geography |

---

## Limitations

- Permitting record completeness varies significantly by jurisdiction. Rural counties and states without centralized energy siting databases have sparser records.
- Asset class specificity matters — a county with a strong solar denial history is not necessarily a strong prior against BESS or data center development. The model applies asset-class weighting where records allow.
- Historical records do not capture informal opposition — deals that never reached a formal application because developers self-selected away from hostile jurisdictions.

---

## See also

- [Variable 1: Community Sentiment](./01-community-sentiment.md) — the forward-looking signal that complements the historical prior
- [Variable 3: Regulatory & Zoning Environment](./03-regulatory-zoning.md) — the formal regulatory context within which the historical record was produced
