# Variable 7: Demographic & Socioeconomic Composition

**Predictive weight: Secondary**
**Model role: Contextual signal — provides additional variance explanation alongside primary variables**

---

## Summary

Race, income, homeownership rates, and educational attainment provide secondary predictive signal in US datasets. This variable is intentionally weighted as secondary — demographic context adds explanatory power at the margins but is not a primary driver of opposition probability when sentiment (Variable 1) and permitting history (Variable 2) are present.

Demographic signals are applied with care to avoid proxying for race or income in ways that could introduce discriminatory scoring patterns. The model uses demographic context to calibrate Bayesian priors, not to penalize communities.

---

## Key findings

### Stokes et al. (2023) — *PNAS*

- Demographic variables (income, race, education, homeownership) explain meaningful variance in opposition outcomes in US datasets after controlling for sentiment and procedural history — but the marginal contribution is small.
- Homeownership rate is the strongest demographic predictor: high homeownership communities show higher organized opposition rates, likely because homeowners have greater financial stake in perceived property value impacts.
- The relationship between income and opposition is non-linear. Both high-income and low-income communities show elevated opposition rates compared to middle-income communities, for different reasons — high-income communities due to property value concerns, low-income communities due to cumulative burden effects.

### Hernandez (2015) — *Renewable and Sustainable Energy Reviews*
**"Sacrifice along the sun belt"**

- Documents differential siting patterns by community demographics. Lower-income and higher-minority-population communities are disproportionately selected for utility-scale solar siting.
- These communities show initially lower formal opposition rates (fewer organizational resources) followed by higher rates of post-approval legal challenges and operational hostility.

---

## Data sources used in LANDMARQ model

| Source | Signal extracted |
|--------|-----------------|
| US Census Bureau (ACS 5-year) | Income, race, education, homeownership by county |
| EPA EJSCREEN | Environmental justice index, cumulative burden percentiles |

---

## Methodological note

LANDMARQ applies demographic variables as contextual modifiers to county-level Bayesian priors, not as direct scoring inputs. The model does not score parcels based on the racial or income composition of surrounding communities as a standalone signal. Demographic context is used only to calibrate how sentiment and permitting history signals should be weighted in specific geographic contexts.

This approach is documented here for full transparency. If you have concerns about how this variable is applied, contact [admin@landmarq.io](mailto:admin@landmarq.io).

---

## Limitations

- County-level demographic data from the Census ACS is updated on a 5-year rolling basis — it does not reflect rapid demographic shifts in fast-growing counties.
- The relationship between demographics and opposition behavior is the most contested finding in the literature. The model weights this variable conservatively as a result.
- Applying demographic signals requires careful monitoring for disparate impact. LANDMARQ reviews this variable's contribution to scores as part of ongoing model governance.

---

## See also

- [Variable 6: Cumulative Burden](./06-cumulative-burden.md) — closely related signal, often co-occurring in environmental justice contexts
- [Variable 1: Community Sentiment](./01-community-sentiment.md) — primary signal that demographic context modifies
