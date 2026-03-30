# Step 1

This folder contains the Step 1 pipeline assets for the AISTER crowdsourcing pilot.

## Overview

This step consists of two main Jupyter notebooks that process and prepare metadata for the AISTER crowdsourcing pilot.

### 1. Metadata Extraction from Europeana

- **Notebook:** `01_metadata_extraction_from_europeana.ipynb`
- **Description:**  
    This notebook connects to the Europeana API to retrieve metadata records relevant to the pilot. It processes the raw API responses, extracts relevant fields, and saves the cleaned metadata in a structured format (e.g., CSV or JSON) for further analysis.

### 2. Tag Extraction from Metadata

- **Notebook:** `02_tag_extraction_from_metadata.ipynb`
- **Description:**  
    This notebook takes the structured metadata produced in the previous step and analyzes it to extract tags. These tags are derived from specific metadata fields and are intended to facilitate later stages of the crowdsourcing workflow. The output is a dataset enriched with tags, ready for use in subsequent steps.

## How to Run

1. Open `01_metadata_extraction_from_europeana.ipynb` and follow the instructions to extract and save metadata.
2. Open `02_tag_extraction_from_metadata.ipynb` to process the metadata and generate tags.

## Output

- Cleaned metadata file (CSV/JSON)
- Tagged metadata file for use in later steps
