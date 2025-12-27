# Plot ETmiss for Open Data dataset

Plot the missing transverse energy (ETmiss) distribution for all events in the specified Open Data dataset.

## Data Samples

| Data Sample | Derivation | Role(s) In Analysis |
| --- | --- | --- |
| user.zmarshal:user.zmarshal.364702_OpenData_v1_p6026_2024-04-23 | PHYSLITE | Data |

## Histograms

1. ETmiss
    * x Axis
        * Missing transverse energy magnitude for each event.
        * `$E_T^{miss}$ [GeV]`
        * Default binning: 0 to 500 GeV in 50 bins.
        * One entry per event.

## Analysis Steps

1. Event selection
    * No selection; include all events.
1. ETmiss
    * Read event-level missing transverse energy.

## Workflow

1. Data Extraction and NTuple Skimming
    * Filtering: No Filtering.
    * Variables: event-level ETmiss (magnitude) and any required metadata for dataset bookkeeping.
2. Data Analysis & Histogramming
    * Fill ETmiss histogram with one entry per event.

## Statistical Analysis

None.

## Tools

* servicex
  * Use func_adl to access the specified dataset and retrieve ETmiss.
* awkward
  * Event-level array handling.
* hist
  * Fill and store histogram as PNG.
* vector
  * Not required unless ETmiss needs vector construction; only use if needed.
