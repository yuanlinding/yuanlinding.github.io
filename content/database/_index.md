---
title: "Novel Magnets Database"
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

The SST classification scheme is described in
[Yuan *et al.*, *Phys. Rev. Mat.* **5**, 014409 (2021)](https://journals.aps.org/prmaterials/abstract/10.1103/PhysRevMaterials.5.014409).
Among the SST types, collinear **SST-4x** corresponds to **altermagnets**, and collinear
**SST-4y** are compensated magnets with non-relativistic spin splitting throughout the
Brillouin zone, as introduced in
[Yuan *et al.*, *Phys. Rev. Lett.* **133**, 216701 (2024)](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.133.216701).

Symmetry analysis uses [FINDMAGSYM](https://findmagsym.streamlit.app/).
Use the search box to filter by formula, MSG symbol, irrep, or SST type.
Use the SST dropdown to restrict to a single class. Click any column header to sort.

{{< sst-table >}}
