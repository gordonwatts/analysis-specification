# {{Analysis/Workflow Name}}

{{Short description of the analysis (no more than 2 lines)}}

## Data Samples

{{List all the data samples that are needed for this work below in the table. If the dataset has been explicitly named, include that too so the information is not lost.}}

| Data Sample | Role(s) In Analysis |
| --- | --- |
| {{ds 1}} | {{Signal/Background, Control Region, etc.}}
| {{ds 2}} | {{Signal/Background, Control Region, etc.}}

## Histograms

{{List each histogram that should be produced as a summary histogram. These may be used as input into a statistical analysis or just a cross checks.}}

1. {{Histogram 1 Title}}
    * x Axis
        * {{Detailed description of what should be plotted}}
        * {{Label for axis, including units if unit-full quantity (e.g. `$p_T$ [GeV]`, or `$\eta$`) - use LaTeX formatting for labels}}}
        * {{Info on binning and axis limits if known}}
        * {{Info on how many entries per event, or per combination in an event, etc.}}
    * {{List other axes here}}
2. {{Histogram 2 Title}}
    * x Axis
        * ...

## Analysis Steps

{{Turning the event data into the histogram often requires complex manipulations. If any high level manipulations are required, they should be listed here. They should be broken down into reusable calculations as makes most sense.}}

1. {{Variable Name}}
    * {{Calculated}}
2. {{Variable Name}}
    * ...

## Workflow

{{List the steps that are required to process the files to put together the final set of histograms}}

1. {{Step Name}}
    * {{What should be done (e.g. process all signals into separate sets of histograms)}}
2. {{Step Name}}
    * ...

## Statistical Analysis

{{List the statistical analysis (if any) that needs to be done on the previous data}}

## Tools

{{This section is a series of bullet points giving some guidance to the tools that should be used to accomplish previous parts.}}

* {{tool 1}}
  * {{Any comments about its usage}}
* {{Tool 2}}
  * ...
