# Variable 1: Community Sentiment & Political Climate

**Predictive weight: Highest**
**Model role: Primary opposition signal — NLP-scored from public text sources**

---

## Summary

Community sentiment and political climate are the strongest predictors of whether a renewable energy or infrastructure project will face organised opposition. This finding is consistent across multiple peer-reviewed datasets covering North American siting outcomes.

The key insight from the literature is that opposition is not primarily ideological in the partisan sense — it is relational. Communities that feel excluded from decision-making, perceive the process as unfair, or have pre-existing distrust of industrial development generate opposition regardless of party affiliation or demographic composition.

This variable is operationalised in the LANDMARQ model through NLP scoring of publicly available text: town hall meeting minutes, local news coverage, elected official statements, and prior ballot outcomes on related issues.

---

## Key findings

### Stokes, Loewen & Soroka (2023) — *PNAS*
**"Public opinion, renewable energy, and local opposition"**

The most comprehensive North American dataset on this question. Key findings:

- Community sentiment toward industrial development is the single strongest predictor of organised opposition in renewable energy siting.
- Opposition is not uniformly driven by partisan ideology. Local sentiment — shaped by place attachment, procedural fairness perceptions, and prior engagement history — is a distinct and more predictive axis.
- Sentiment measured at the county level from public records shows significant geographic clustering, suggesting that opposition patterns are persistent across project cycles in the same jurisdiction.
- The study found no statistically significant relationship between community demographics and opposition rates after controlling for sentiment and procedural history.

**Implication for LANDMARQ:** Sentiment measured from public text — town hall minutes, local news — provides a stronger predictive signal than demographic or ideological proxies. This justifies NLP scoring as the primary data collection method for Variable 1.

---

### Baxter, Morzaria & Hirsch (2013) — *Energy Policy*
**"A case study of public acceptability of renewable energy"**

- Distinguishes between *general* support for renewable energy (consistently high in surveys) and *local* opposition to specific projects (consistently underestimated from survey data alone).
- The "social gap" between stated support and actual opposition behavior is driven primarily by perceived conflict with local identity and place attachment — factors that do not show up in standard demographic surveys.
- Opposition mobilization is triggered not by the project itself but by the perceived legitimacy of the decision-making process.

**Implication for LANDMARQ:** Sentiment measurement must focus on the local, project-specific record — not regional or national survey data. Town hall minutes and local news capture the specific mobilization dynamic that national surveys miss.

---

### Devine-Wright (2011) — *Wiley Interdisciplinary Reviews: Climate Change*
**"Renewable Energy and the Public"**

- Place attachment theory applied to wind energy opposition. Communities with stronger local identity show more intense opposition regardless of their general views on climate change.
- Opposition groups form around local identity narratives, not rational economic objections. This means standard community benefits packages are often insufficient to neutralize organized opposition once it has formed.
- The timing of engagement matters as much as the substance — communities that learn about a project from media or neighbors rather than directly from the developer have systematically higher opposition rates.

**Implication for LANDMARQ:** Early sentiment signals — particularly whether a community has pre-existing awareness of development pressure — are predictive of opposition formation, not just its intensity.

---

## Data sources used in LANDMARQ model

| Source | Signal extracted | Method |
|--------|-----------------|--------|
| County planning meeting minutes | Opposition fingerprints, recurring objectors, organized group names | NLP keyword and entity extraction |
| Local news coverage (3-year lookback) | Coverage volume, framing, community mobilization signals | NLP sentiment and topic modeling |
| Elected official statements | Prior positions on industrial development, regulatory posture | NLP named entity + stance detection |
| Prior ballot outcomes | Historical record of community votes on comparable issues | Boolean + recency weighting |

---

## Limitations

- NLP scoring quality depends on the availability and completeness of public text records. Rural counties with limited local news coverage or incomplete meeting minute archives produce weaker sentiment signals.
- Sentiment is measured at a point in time. New organizing activity or political change after score generation is not captured.
- The model does not distinguish between latent opposition (residents who dislike the project) and activated opposition (residents who will show up to a town hall). The research suggests these are correlated but not identical.

---

## See also

- [Variable 2: Historical Permitting Outcomes](./02-historical-permitting.md) — complements sentiment signal with jurisdictional track record
- [Variable 4: Community Equity & Engagement](./04-community-equity.md) — early engagement as a mitigant to sentiment-driven opposition
