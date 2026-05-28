---
title: "Spin Polarized Magnets"
date: 2026-05-28
summary: |
  Interactive database of ~2,400 experimentally determined spin-polarized magnets
  with SST classification, magnetic space group, Néel temperature, and literature reference.
---

This database collects magnetic crystal structures from
[MAGNDATA](https://cryst.ehu.es/magndata) and augments them with
spin-splitting type (SST-1 through SST-7) classification, magnetic space group
symmetry with and without spin-orbit coupling (SOC), spin space group, magnetic
irreducible representation, and experimental Néel temperature.

The SST classification scheme is described in
[Yuan *et al.*, *Phys. Rev. X* **14**, 011019 (2024)](https://doi.org/10.1103/PhysRevX.14.011019).
Symmetry analysis uses [FINDMAGSYM](https://findmagsym.streamlit.app/).

Use the search box to filter by formula, MSG symbol, irrep, or SST type.
Use the dropdown to restrict to a single SST class.
Click any column header to sort. MAGNDATA entries link to the original
structure page on the Bilbao Crystallographic Server.

{{< sst-table >}}
