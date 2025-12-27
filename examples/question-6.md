# Trijet Top Candidate pT and Max b-tag in Closest-mass Trijet

Select events with at least three jets and, per event, build all trijet combinations to find the one with invariant mass closest to 172.5 GeV. Plot the trijet pT and the maximum b-tagging discriminant among the jets in that trijet.

## Data Samples

| Data Sample | Derivation | Role(s) In Analysis |
| --- | --- | --- |
| opendata:mc20_13TeV.410471.PhPy8EG_A14_ttbar_hdamp258p75_allhad.deriv.DAOD_PHYSLITE.e6337_s3681_r13167_p6026 | PHYSLITE | Signal (ttbar all-hadronic) |

## Histograms

1. Trijet pT (closest-mass trijet)
    * x Axis
        * Transverse momentum of the trijet four-momentum whose invariant mass is closest to 172.5 GeV in each event.
        * `$p_T^{3j}$ [GeV]`
        * Binning: 50 bins, 0 to 500 GeV.
        * One entry per event (if at least one trijet exists).
2. Max b-tag discriminant in closest-mass trijet
    * x Axis
        * Maximum b-tagging discriminant value among the three jets in the selected trijet.
        * `max b-tag discriminant`
        * Binning: 50 bins, 0 to 1 (normalized discriminant).
        * One entry per event (if at least one trijet exists).

## Analysis Steps

1. Event and jet selection
    * Require at least three jets passing baseline selection.
    * Use jets with pT > 25 GeV and |eta| < 2.5.
2. Build trijet combinations
    * For each event, build all 3-jet combinations and compute their invariant mass and trijet four-momentum.
3. Closest-mass trijet selection
    * Select the trijet with invariant mass closest to 172.5 GeV.
4. Derived quantities
    * Trijet pT from the selected trijet four-momentum.
    * Max b-tag discriminant from the three jets in the selected trijet.

## Workflow

1. Data Extraction and NTuple Skimming
    * Filtering: keep only events with at least three jets passing baseline selection.
    * Variables: jet pt, eta, phi, mass, and b-tag discriminant (exact field name to be specified).
2. Data Analysis & Histogramming
    * Build trijet combinations, compute mass and pT, select closest to 172.5 GeV.
    * Compute max b-tag discriminant in the selected trijet.
    * Fill the two histograms with one entry per selected event.

## Statistical Analysis

None.

## Tools

* servicex (func_adl)
  * Extract PHYSLITE jets and apply event/jet filtering.
* awkward
  * Build combinations and select closest-mass trijet.
* vector
  * Compute trijet four-momenta, mass, and pT.
* hist
  * Fill and save histograms as PNG.
