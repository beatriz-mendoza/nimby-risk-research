# Methodology Notes

**How academic research maps to model weights and signal design.**

This document bridges the evidence base (peer-reviewed literature) and the operational model (LANDMARQ scoring engine). It explains the translation choices — where we followed the literature directly, where we made practical compromises, and where the model deviates from academic findings.

---

## Translation principles

### 1. Research identifies variables. Data availability determines operationalisation.

The academic literature identifies community sentiment as the strongest predictor of opposition. But "community sentiment" as measured in academic studies (surveys, interviews, ethnographic research) is not available at scale for thousands of parcels in real time.

The operational translation — NLP scoring of town hall meeting minutes and local news — is a proxy. It captures organised opposition signals and political climate indicators that are available at scale and auditable. It does not capture private sentiment (what residents say to each other, not in public records).

This is a documented limitation. The model is not a measurement of community sentiment in the academic sense. It is a measurement of publicly observable signals correlated with that sentiment.

### 2. Weights are calibrated, not derived.

Model weights are not read directly from published effect sizes. The literature provides a relative ordering (sentiment > history > regulatory environment) and a sense of magnitude, but direct application of published coefficients would require identical data collection methodologies — which we do not have.

Instead, weights are initialized from the literature's relative ordering and then calibrated against the labeled outcome dataset using Bayesian updating. The current calibration (n=30) produces weight ranges rather than point estimates. As the training dataset grows, confidence intervals will narrow.

### 3. The model scores parcels, not projects.

Academic studies typically analyze project-level outcomes — the result of a specific developer proposing a specific project at a specific time. The LANDMARQ model scores parcels before any developer or project is specified.

This means the model captures the baseline opposition risk of a location, not the incremental risk added by project-specific factors (developer reputation, project scale, community engagement quality). Some of those factors are captured as signals (community equity variable includes developer engagement quality as an input) but the model is fundamentally a location-level prior, not a project-level prediction.

---

## Signal design decisions

### Why NLP on town hall minutes rather than social media?

Town hall meeting minutes are:
- Officially recorded and archived
- Attributable to specific jurisdictions and dates
- Less susceptible to astroturfing and coordinated inauthentic behavior
- Available for historical lookback (5–10 year windows possible)

Social media is more real-time but has significant noise problems for this use case. A single viral post can generate thousands of signals that do not represent the actual organized opposition landscape in a county.

We use local news coverage as a secondary NLP source. Local news provides structured narrative around opposition events (organized groups, legal filings, public meetings) that town hall minutes may not fully capture.

### Why prior ballot outcomes?

Prior ballot outcomes on comparable issues (moratoriums, land use restrictions, zoning changes) provide a rare ground-truth signal: how a community actually voted, not just what they said in meetings. Ballot outcome data is sparse (most opposition does not reach ballot) but highly informative when present.

### Why not satellite imagery or visual analysis?

Visual impact is captured through GIS proximity modeling rather than satellite imagery analysis. Full sight-line rendering (viewshed analysis) is on the v2 roadmap. Current pilot deployment uses distance-to-residential-zone as a proxy.

Satellite imagery adds significant computational cost for marginal signal improvement over GIS proximity in the current model architecture. This will be revisited as the model scales.

---

## Known gaps

| Gap | Impact | Mitigation |
|-----|--------|------------|
| NLP quality varies with data availability | Rural counties with sparse public records produce weaker sentiment signals | Confidence interval widening for data-sparse geographies |
| Developer-reported inputs are unverified | Community equity variable has self-reporting bias | Developer inputs flagged in parcel reports; conservative variable weighting |
| n=30 training dataset | Wide confidence intervals on weight estimates | Reported as ranges; investor/client disclosure |
| US onshore only | Performance in offshore, tribal, international contexts unvalidated | Documented geographic scope limitation |
| No post-score updating | Events after scoring not captured | Recommended re-score cadence of 90 days for active diligence |

---

*For questions on methodology: [admin@landmarq.io](mailto:admin@landmarq.io)*
*Full model disclaimer: [landmarq.io/disclaimer](https://landmarq.io/disclaimer)*
