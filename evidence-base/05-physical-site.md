# Variable 5: Physical & Site Characteristics

**Predictive weight: Medium**
**Model role: Proximity and visibility signal — determines who gets mobilized**

---

## Summary

Physical visibility and proximity to sensitive uses determine who shows up to oppose a project. Two parcels with identical zoning, sentiment scores, and permitting histories can face very different opposition levels based purely on how many residents can see the project and how close it is to schools, hospitals, or residential zones.

---

## Key findings

### Roddis, Carver, Dallimer, Norman & Ziv (2018) — *Applied Energy*
**"The role of community acceptance in planning outcomes for onshore wind turbines"**

- GIS-based visibility analysis is the strongest site-level predictor of organized opposition. Projects visible from a high number of residential properties face systematically higher opposition rates than comparable projects with lower visual exposure.
- Proximity to sensitive receptors (schools, hospitals, residential zones) amplifies perceived health and safety concerns independent of actual risk levels.
- The relationship is not linear — opposition rises sharply above certain proximity thresholds (typically 0.5–1 mile for most asset classes) rather than increasing smoothly with distance.

### Guo, Tong, Zhang & Qi (2024) — *PNAS*
**"Visual impact and community opposition in energy infrastructure siting"**

- Most recent comprehensive dataset. Confirms visibility as primary site-level predictor. Finds that viewshed size (number of residential parcels with line-of-sight to project) explains more variance in opposition outcomes than any other physical characteristic.
- Topography matters: projects in valleys or screened by terrain face significantly lower opposition than ridge-sited or flat-land projects of comparable scale.

---

## Data sources used in LANDMARQ model

| Source | Signal extracted |
|--------|-----------------|
| HIFLD / county GIS layers | Proximity to residential zones, schools, hospitals |
| Parcel boundary data | Setback compliance assessment |
| USGS terrain data | Topography and screening analysis |

*Note: Full sight-line rendering is the target methodology. Current pilot deployment uses distance-to-residential proxy pending GIS pipeline completion.*

---

## Limitations

- Visibility modeling at full parcel resolution requires significant computational resources. The current pilot uses distance-based proxies rather than true viewshed analysis.
- Proximity thresholds vary by asset class — wind turbines, solar arrays, BESS installations, and data centers each have different visual and acoustic impact profiles that affect who mobilizes to oppose them.
- The model does not currently account for intervening terrain or vegetation screening between the parcel and residential zones.

---

## See also

- [Variable 6: Cumulative Burden](./06-cumulative-burden.md) — regional saturation compounds physical site risk
- [Variable 3: Regulatory & Zoning Environment](./03-regulatory-zoning.md) — setback requirements as a regulatory proxy for physical risk
