# Mars Solar Microgrid Sizing Model — Version 9

An interactive first-order sizing calculator by Yiran Gao for a solar-first microgrid serving an illustrative 1,000-person Mars settlement.

The calculator estimates settlement energy demand, average load, active photovoltaic area, reference-condition output, battery capacity, and survival-bus backup power. Users can vary population, per-capita demand, equivalent full-sun hours, and the combined photovoltaic retention factor.

## Use the calculator

Open `index.html` in a modern web browser. All calculations run in the browser; no installation, account, server, or external library is required.

The live calculator now provides a Version 9 advanced-scenario interface powered by `mars-microgrid-scenario-v9.json`, with editable parameters and JSON import/export. Its underlying first-order sizing methods have been extended for editable loss and capacity assumptions, while the new operational metrics remain simplified exploratory estimates.

## Baseline

| Input | Value |
| --- | --- |
| Population | 1,000 people |
| Per-capita electricity demand | 60 kWh/person/sol |
| Equivalent full-sun hours | 3.0 h/sol |
| Combined photovoltaic retention factor | 0.65 |
| Reference irradiance | 590 W/m² |
| Photovoltaic cell efficiency | 30% |
| Usable storage autonomy | 2 sols |

The baseline gives 60 MWh/sol of demand, approximately 0.174 km² of active photovoltaic area, 20.0 MW of derated reference-condition output, 120 MWh of usable storage, approximately 231 MWh of battery nameplate capacity, and two conceptual 1.5 MW backup trains.

## Scope

This is a deterministic preliminary sizing model. It does not calculate site-specific sunlight, time-dependent battery operation, dust-storm performance, equipment failure probabilities, loss-of-load probability, or expected unserved energy. The calculations do not establish feasibility or quantitative reliability. Active photovoltaic area excludes field spacing and supporting infrastructure.

## Publish with GitHub Pages

1. Create a public repository named `mars-solar-microgrid`.
2. Upload `index.html`, this `README.md`, and `.nojekyll` to the root of the `main` branch.
3. Open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**, select **main** and **/(root)**, and save.
5. After deployment completes, open the website address shown in Pages settings.

Official instructions: https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site

## Research citation

For a permanent software citation, archive the exact model version used for the manuscript in a research repository such as Zenodo and cite the resulting DOI. The GitHub Pages address provides access to the live calculator; it does not imply peer-reviewed publication.

## Version 9 scenario file and limitations

The default scenario configuration is stored in `mars-microgrid-scenario-v9.json`. Open the **Version 9 · Advanced scenario** panel to adjust assumptions or import/export a Version 9 JSON file. The first-order dashboard includes updated PV and battery sizing inputs, while the additional operational panel supplies approximate PV footprint, storage energy, backup capacity and storm deficit estimates.

**Important:** The advanced panel is not a validated time-resolved or probabilistic reliability model. Parameters including seasonal cycles, failure availability, backup path availability, charging caps and time-step resolution are stored and exposed but not fully integrated into a chronological dispatch simulation. Storm-related estimates use simplified daily energy balances, not SOC trajectories. Avoid presenting those outputs as LOLP, EENS or confirmed Mars mission feasibility.
