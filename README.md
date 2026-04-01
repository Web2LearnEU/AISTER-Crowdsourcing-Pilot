# AISTER-Crowdsourcing-Pilot
Small-scale study implementing and analysing an experimental digital humanities workflow that combines AI tools (natural language proccessing, machine vision) and human-in-the-loop processes, to enhance the accessibility and discoverability of Ukrainian ethnographic heritage by improving the quality of descriptive metadata.

## Workflow Steps Overview

### Step 1: Text-based metadata enrichment
- Fetch structured metadata for the folk paintings dataset from the Europeana API
- Prepare the dataset for tag extraction through feature engineering
- Extract candidate tags from title and description using NLP (spaCy - NER)

### Step 2: Image enrichment
- Download images of folk paintings using their ids (fetched via the API)
- Generate captions for images using image recognition and machine vision
- Extract candidate tags from the machine-generated caption