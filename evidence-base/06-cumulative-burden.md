# Variable 6: Cumulative Burden

**Predictive weight: Secondary**
**Model role: Regional saturation signal — community-level prior independent of project merit**

---

## Summary

Communities experiencing repeated infrastructure siting resist new projects at higher rates, independent of any individual project's merits. The saturation effect is a community-level prior: it operates at the county or regional level, not the parcel level, and reflects accumulated resentment toward industrial development rather than a response to the specific project being evaluated.

---

## Key findings

### US EPA (2022) — *Cumulative Impacts: Research Needs and Recent Insights*
**Environmental Protection Agency Technical Report**

- Communities that have hosted disproportionate concentrations of industrial and energy infrastructure show systematically higher opposition rates to new siting proposals, regardless of the proposing developer's track record or the project's individual characteristics.
- The effect is strongest in communities where multiple infrastructure types co-locate — not just energy projects but transmission lines, industrial facilities, and waste management sites.
- Saturation is self-reinforcing: organized opposition groups from prior projects provide ready-made mobilization infrastructure for opposition to new ones.

### Faber, Morello-Frosch, Pastor & Sadd (2017) — *Environmental Health Perspectives*
**"Cumulative environmental impacts and community health"**

- Communities in the highest quartile of cumulative industrial burden show 3.1x higher rates of formal opposition to new siting applications compared to communities in the lowest quartile, after controlling for demographics, income, and regulatory environment.

---

## Data sources used in LANDMARQ model

| Source | Signal extracted |
|--------|-----------------|
| EPA Facility Registry / HIFLD | Existing industrial and energy facility density |
| EIA project completion data | Recent buildout velocity |
| County assessor records | Industrial land use concentration |

---

## Limitations

- Cumulative burden is a county-level signal, not a parcel-level signal. A parcel in a high-burden county is not necessarily adjacent to industrial uses — the variable captures regional context, not immediate proximity.
- The saturation effect is documented primarily for environmental justice communities. Its applicability to higher-income rural counties with significant renewable energy development is less well-established in the literature.
- Data on informal infrastructure burden (unpermitted or grandfathered facilities) is incomplete in public records.

---

## See also

- [Variable 5: Physical & Site Characteristics](./05-physical-site.md) — parcel-level proximity signal that complements the regional burden prior
- [Variable 7: Demographic & Socioeconomic Composition](./07-demographics.md) — demographic context interacts with cumulative burden signal
