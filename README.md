# Pecos Model Ledger

Technical calibration-status ledger for the Pecos River basin SWAT+/gwflow model (rev 62, gwflow-coupled). Every
panel is computed from finished model runs against real USGS daily flow and, in the Salinity section, real USGS
Water Quality Portal grab samples — not illustrative or idealized data.

**Live demo:** https://josephauresy.github.io/pre_calibration_pecos/

## What it covers

- **Flow**: how much, when, and what shape the flow bias takes at each gauge; groundwater vs. observation wells;
  water balance; evapotranspiration; missing-process diagnosis (v31/v32); parameter ledger and version history;
  calibration design and experiments; a "ready to calibrate?" readiness check.
- **Salinity**: SWAT+'s native 8-ion salt transport (TDS = sum) + gwflow groundwater exchange + two point sources
  (Malaga Bend brine, produced water) — development history (bug fixes that had to happen before a mass-conserving
  run was possible), source inventory, water/salt balance, real observation comparison, remaining uncertainties, and
  calibration readiness. A 26-year production run (`v52_prod`, 2000–2025) is numerically stable and mass-conserving,
  but flagged **"ready with caveats"** — biased 1.06–3.6× high at the two assessable gauges (Red Bluff, Orla/ch82),
  traced to unverified initial-condition and point-source assumptions rather than a code defect.
- **Salinity Atlas**: native SVG maps (monitoring stations, initial groundwater salinity, source locations,
  groundwater-to-stream pathways, per-reach export) and observed-vs-simulated figures for the same run.

## Audience

This is the model developer's own technical working document — bug tracker, parameter ledger, calibration-readiness
calls — not a stakeholder-facing tool. For that, see the related tools below.

## Related tools (Pecos modeling suite)

- **[Pecos Reservoir Management & Reuse Lab](https://josephauresy.github.io/pecos-reservoirs/)** — real observed
  reservoir flow/storage/release data and a reuse-siting tool for the 5 major Pecos dams, plus the
  **[Red Bluff Reservoir Modeling Hub](https://josephauresy.github.io/pecos-reservoirs/red-bluff-reservoir-hub.html)**
  (data-readiness for a Delft3D-FM model of Red Bluff specifically — its Salinity & WQ tab reproduces this ledger's
  Red Bluff numbers alongside real inflow/outflow/water-level data this ledger doesn't carry).
- **[Pecos Basin Salinity Transport — Stakeholder Lab](https://josephauresy.github.io/pecos-salinity-lab/)** — an
  idealized 2-D teaching simulation of the same salt-transport physics, built for stakeholder engagement, not fit to
  observed data the way the run documented here is.

## Running locally

No build step. Serve the folder with any static file server, e.g. `python -m http.server 8732`, then open
`http://localhost:8732/`.
