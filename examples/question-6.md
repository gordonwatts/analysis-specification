# Trijet Closest-to-Top pT and Max b-tag Discriminant

Select events with at least three jets, form all trijet combinations, choose the trijet whose invariant mass is closest to 172.5 GeV, then plot its pT and the maximum b-tag discriminant among its jets for the specified dataset.

## Data Samples

| Data Sample | Derivation | Role(s) In Analysis |
| --- | --- | --- |
| opendata:mc20_13TeV.410471.PhPy8EG_A14_ttbar_hdamp258p75_allhad.deriv.DAOD_PHYSLITE.e6337_s3681_r13167_p6026 | PHYSLITE | Signal / study sample |

## Histograms

1. Trijet pT (closest to 172.5 GeV)
    * x Axis
        * pT of the trijet four-momentum for the trijet with invariant mass closest to 172.5 GeV in each event with >=3 jets
        * `$p_T^{3j}$ [GeV]`
        * 
        * One entry per event (events with >=3 jets)
2. Max b-tag discriminant in selected trijet
    * x Axis
        * Maximum b-tagging discriminant value among the three jets in the selected trijet
        * `max b-tag discriminant`
        * 
        * One entry per event (events with >=3 jets)

## Analysis Steps

1. Jet Selection
    * Select jets per event, then require events with at least three selected jets
2. Trijet Candidate Selection
    * Build all trijet combinations, compute invariant mass for each, and choose the trijet with mass closest to 172.5 GeV
3. Trijet pT
    * Compute the pT of the selected trijet four-momentum
4. Max b-tag Discriminant
    * Compute the maximum b-tag discriminant among the three jets in the selected trijet

## Workflow

1. Data Extraction and NTuple Skimming
    * Filtering: Keep events with at least three selected jets
    * Variables: jet four-momentum components (pt, eta, phi, mass or energy), jet b-tagging discriminant, and any jet selection flags required
2. Data Analysis & Histogramming
    * Build trijet combinations, compute invariant masses, select closest to 172.5 GeV
    * Compute trijet pT and max b-tag discriminant, then fill the histograms

## Statistical Analysis

None.

## Tools

* servicex (func_adl)
  * Query PHYSLITE and apply the event-level >=3 jet filter at the source
* awkward
  * Build trijet combinations and per-event selection
* vector
  * Four-momentum construction and invariant mass, pT computations
* hist
  * Histogram filling and PNG output
