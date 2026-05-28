---
title: "Novel Magnets"
date: 2026-05-28
summary: |
  Interactive database of ~1,800 experimentally determined magnetic materials
  with SST classification, magnetic space group, Néel temperature, and literature reference.
---

<style>article.prose h1:first-of-type { display: none !important; }</style>

This database collects experimentally determined magnetic crystal structures from
[MAGNDATA](https://cryst.ehu.es/magndata) and classifies each by its
spin-splitting type (SST), magnetic space group symmetry with and without
spin-orbit coupling (SOC), spin space group, magnetic irreducible representation,
and experimental Néel temperature.

**SST classification** ([Yuan *et al.*, *Phys. Rev. Mat.* **5**, 014409 (2021)](https://journals.aps.org/prmaterials/abstract/10.1103/PhysRevMaterials.5.014409)) is determined by the magnetic space group type and the presence of time-reversal × inversion (Θ·I) symmetry:

- **SST-1 / SST-2**: Collinear compensated magnets with Θ·I — no spin splitting at any wavevector
- **SST-3**: Collinear compensated magnets without Θ·I — relativistic spin splitting only
- **SST-4x**: Collinear compensated magnets with non-relativistic spin splitting throughout the Brillouin zone — these are the **altermagnets**
- **SST-4y**: Collinear compensated magnets with non-relativistic spin splitting specifically at the Brillouin zone center Γ, as introduced in [Yuan *et al.*, *Phys. Rev. Lett.* **133**, 216701 (2024)](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.133.216701)
- **SST-5**: Uncompensated magnets (ferrimagnets, ferromagnets)

Symmetry analysis uses [FINDMAGSYM](https://findmagsym.streamlit.app/).
Use the search box to filter by formula, MSG symbol, irrep, or SST type.
Use the SST dropdown to restrict to a single class. Click any column header to sort.

{{< sst-table >}}
