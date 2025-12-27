# Reconstructed $t\bar{t}$ Mass Near 3 TeV (Single-Lepton Channel)

Plot the reconstructed $t\bar{t}$ invariant mass near 3 TeV in single-lepton events from the specified Rucio dataset.

## Data Samples

| Data Sample | Derivation | Role(s) In Analysis |
| --- | --- | --- |
| user.zmarshal:user.zmarshal.301333_OpenData_v1_p6026_2024-04-23 | PHYSLITE | Data (signal region) |

## Histograms

1. Reconstructed $m_{t\bar{t}}$ (single-lepton)
    * x Axis
        * Reconstructed invariant mass of the $t\bar{t}$ system in the single-lepton channel, using one leptonic top and one hadronic top reconstruction.
        * `$m_{t\bar{t}}$ [GeV]`
        * Proposed range 2000-4000 GeV with 40-80 bins (adjustable).
        * One entry per selected event (best combination per event).

## Analysis Steps

1. Event Selection
    * Exactly one isolated charged lepton (electron or muon).
    * Missing transverse momentum consistent with leptonic $W$ decay.
    * At least 4 jets, with at least 2 b-tagged jets (working point TBD).
2. Object Definitions
    * Identify jets, b-tagged jets, leptons, and missing transverse momentum (MET).
3. Leptonic Top Reconstruction
    * Use lepton + MET to reconstruct $W \to \ell\nu$ (solve neutrino $p_z$ with $m_W$ constraint).
    * Combine leptonic $W$ with a b-tagged jet to form leptonic top candidate.
4. Hadronic Top Reconstruction
    * From remaining jets, choose a b-tagged jet + two non-b jets to form hadronic top candidate.
5. Combination Choice
    * Select the combination minimizing a chi2-like metric (e.g., deviations from $m_W$ and $m_t$).
6. $t\bar{t}$ Mass
    * Combine leptonic and hadronic top four-vectors to form $m_{t\bar{t}}$.

## Workflow

1. Data Extraction and NTuple Skimming
    * Filtering: Require at least 1 lepton and at least 4 jets at the source if possible.
    * Variables: lepton 4-vectors and IDs, jet 4-vectors, b-tag flags, MET and MET phi, event weights if any, run/lumi/event identifiers.
2. Data Analysis & Histogramming
    * Build leptonic and hadronic top candidates per event as described.
    * Apply single-lepton and jet/b-jet selections.
    * Fill the $m_{t\bar{t}}$ histogram with the best combination per event.

## Statistical Analysis

No statistical analysis required beyond the histogram.

## Tools

* servicex (func_adl)
  * Query and skim the PHYSLITE dataset from Rucio.
* awkward
  * Event-level selection, combinatorics, and array operations.
* vector
  * Four-vector reconstruction and invariant mass calculations.
* hist
  * Histogramming and PNG output.
