# analysis-specification

A specification of a particle physics analysis at a LHC-like experiment. A specification is a list of the data, histograms, and calculations that are needed - not a step-by-step plan.

* `analysis-specification-template.md` - A template with instructions
* `examples` - Some examples

## Goals

This specification should:

* be high level
  * Specifies what datasets are needed, but not the actual data set name (e.g. W+Jets, or ttbar + bbar, but not the dataset name).
* be readable by both human and LLM
* possible to be written by both human and LLM
* Cuts may be listed, but they may also say something like "high-pT" rather than "pt > 40 GeV".
* Specific analysis steps, final variables, etc., should be given in enough detail (or be commonly known)
  * ttbar mass plot is probably known well enough
  * m3 variable is not and would need to be detailed.

## Non-Goals

* This is an outline, not a procedural step-by-step.
* No code fragments
* While tools will likely be listed, there should be no step-by-step setup guides, etc.
