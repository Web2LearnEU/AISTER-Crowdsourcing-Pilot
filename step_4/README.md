# Step 4 - Lexical filtering and ethical assessment

Step 4 evaluates validated annotation tags against the DE-BIAS controlled vocabulary to identify potentially biased or sensitive terminology in the Ukrainian Folk Art annotation dataset.

## Overview

The workflow consists of:

1. **Lexical filtering and DE-BIAS vocabulary matching**  
   `debias_annotation_check.ipynb`

The notebook performs:
- RDF vocabulary parsing
- lexical normalization
- rule-based term matching

## Repository Structure

```text
step_4/
  notebooks/
    debias_annotation_check.ipynb

  data/
    5_ukrainian-folkart-annotations.csv
    DE-BIAS_vocabulary.rdf

  outputs/
    de-bias_assessed_final_ukrainian-folkart-annotations-AISTER-pilot-including rejected-annotations.xlsx
```

## Inputs and Outputs

### Inputs
- `5_ukrainian-folkart-annotations.csv`
- `DE-BIAS_vocabulary.rdf`

### Outputs
- `de-bias_assessed_final_ukrainian-folkart-annotations-AISTER-pilot-including rejected-annotations.xlsx`

## Usage

Run:

- `notebooks/debias_annotation_check.ipynb`

The notebook:
- loads annotation records
- parses the DE-BIAS RDF vocabulary
- normalizes labels and vocabulary terms
- performs lexical matching
- exports the assessed spreadsheet

## Limitations

- The workflow performs lexical and not semantic analysis.
- Human review is still required for contextual interpretation.
- The correction of the problematic terms based on the proposed terminology in the DE-BIAS vocabulary is not automated and is performed manually.
