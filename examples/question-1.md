# ETmiss Spectrum for Open Data Sample

Plot missing transverse energy for all events in the specified Open Data dataset.

## Data Samples

All data are drawn from the single rucio dataset named below.

| Data Sample | Role(s) In Analysis |
| --- | --- |
| user.zmarshal:user.zmarshal.364702_OpenData_v1_p6026_2024-04-23 | Data (inclusive, all events) |

## Histograms

1. ETmiss
    * x Axis
        * Missing transverse energy for each event.
        * `$E_T^{miss}$ [GeV]`
        * Proposed binning: 0 to 500 GeV in 50 uniform bins (update if you prefer).
        * One entry per event.

## Analysis Steps

1. ETmiss
    * Read the event-level missing transverse energy from the dataset and use it directly for histogramming.

## Workflow

1. Data access
    * Query the rucio dataset with ServiceX/func_adl and retrieve the needed ETmiss branch.
2. Histogramming
    * Fill the ETmiss histogram for all events.
3. Output
    * Save the histogram as a PNG image.

## Statistical Analysis

None.

## Tools

* servicex (func_adl)
  * Query and skim the dataset, selecting the ETmiss branch.
* awkward
  * Manipulate event arrays and interface with histogramming.
* hist
  * Define and fill the ETmiss histogram; export PNG.
* vector
  * Not required unless ETmiss must be reconstructed from components.
