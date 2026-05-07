# Methodology Notes

**How academic research maps to model design.**

This document outlines the translation principles behind LANDMARQ's scoring engine — 
where we followed the literature directly, where we made practical compromises, 
and where the model deviates from academic findings.

---

## Translation principles

### 1. Research identifies variables. Data availability determines operationalisation.

The academic literature identifies community sentiment as the strongest predictor of 
opposition. But sentiment as measured in academic studies (surveys, interviews, 
ethnographic research) is not available at scale for thousands of parcels in real time.

The operational translation uses NLP scoring of publicly available records — a proxy 
that captures organised opposition signals and political climate indicators at scale. 
This is a documented limitation. The model measures publicly observable signals 
correlated with sentiment, not private sentiment itself.

### 2. Weights are calibrated, not derived.

Model weights are not read directly from published effect sizes. The literature provides 
a relative ordering and a sense of magnitude, but direct application of published 
coefficients would require identical data collection methodologies.

Instead, weights are initialized from the literature's relative ordering and calibrated 
against our proprietary labeled outcome dataset using Bayesian updating. Specific weight 
ranges and calibration details are not disclosed.

### 3. The model scores parcels, not projects.

Academic studies typically analyze project-level outcomes. The LANDMARQ model scores 
parcels before any developer or project is specified — capturing baseline opposition 
risk of a location, not incremental risk added by project-specific factors.

---

## Signal design decisions

### Why NLP on town hall minutes rather than social media?

Town hall meeting minutes are officially recorded, attributable to specific jurisdictions 
and dates, less susceptible to coordinated inauthentic behavior, and available for 
historical lookback. Local news coverage is used as a secondary NLP source for 
structured narrative around opposition events.

### Why prior ballot outcomes?

Prior ballot outcomes on comparable issues provide a rare ground-truth signal — how a 
community actually voted. Ballot outcome data is sparse but highly informative when present.

---

## Scope and limitations

The model is calibrated on US onshore infrastructure. Performance in offshore, tribal, 
or international contexts has not been validated. Specific known limitations and 
confidence interval methodology are disclosed to clients and investors upon request.

---

*For questions on methodology: [admin@landmarq.io](mailto:admin@landmarq.io)*  
*Full model disclaimer: [landmarq.io/disclaimer](https://landmarq.io/disclaimer)*
