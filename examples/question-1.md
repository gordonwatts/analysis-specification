# ETmiss Distribution for Open Data Dataset

  Plot the missing transverse energy (ETmiss) for all events in the specified ATLAS Open Data dataset.

## Data Samples

  | Data Sample | Role(s) In Analysis |
  | --- | --- |
  | user.zmarshal:user.zmarshal.364702_OpenData_v1_p6026_2024-04-23 | Primary data sample |

## Histograms

  1. ETmiss
      - x Axis
          - Missing transverse energy magnitude for each event, taken from the standard MET container in the dataset.
          - $E_T^{miss}$ [GeV]
          - 50 bins from 0 to 500 GeV (default; adjust as needed).
          - One entry per event.

## Analysis Steps

  1. ETmiss
      - Read the event-level MET container and compute the ETmiss magnitude (or use provided MET magnitude field if available).

## Workflow

  1. Extract Data
      - Access the dataset user.zmarshal:user.zmarshal.364702_OpenData_v1_p6026_2024-04-23 and iterate over all events.
        - Perform no cuts on the events
        - Extract ETmiss for each event.
  2. Process the Data
      - Fill the ETmiss histogram with one entry per event.
  3. Output
      - Save the histogram to a file (e.g., Parquet) and produce a plot (PNG).

## Statistical Analysis

  None.

## Tools

- ServiceX + func_adl (optional)
  - Use if data access is remote and xAOD-based.
- Awkward Array + hist (Python)
  - Use for event-level extraction and histogramming.

  Questions to finalize:

  1. Which MET container/term should define ETmiss (e.g., MET_Reference_AntiKt4EMTopo, MET_Reference_AntiKt4EMPFlow, or a dataset-specific
     field)?
  2. Preferred binning and range for ETmiss (keep 0–500 GeV with 50 bins, or specify)?
  3. Output format for the histogram/plot (ROOT, PNG, PDF, Parquet, other)?
  4. Any event cleaning or selection, or truly all events unfiltered?
