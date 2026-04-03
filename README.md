# AISTER Human-In-The-Loop Crowdsourcing Pilot

*The repository contains the complete workflow and files for automatically generating description tags for artefacts on Europeana using AI tools (natural language processing, computer vision), and for running a human-in-the-loop crowdsourcing campaign to validate the tags.* 

##  Pilot description
This case study forms a small-scale exploratory pilot within the field of Digital Humanities / Cultural Heritage Informatics, operationalising and analysing a human-in-the-loop (HITL) crowdsourcing framework for metadata enrichment in Europeana collections. 

## Context
The pilot is part of the AISTER project, “AI-enabled Citizen Participation in University-driven Ukrainian Cultural Heritage Safeguarding”, under the Erasmus+ KA2, Higher Education sector programme. Learn more about the pilot project, the team, collaborating experts and partner institutions, and the workshops conducted: https://web2learn.eu/crowdsourcing-campaign-aister  

## Who can use the repository and how
The repository is designated as an open-source resource for digital humanities research, freely available for reproduction or reuse by scholars, students, and teachers. It is also intended for creative reuses.

## Repository description
The pilot consists of 3 technical steps, each documented in its respective folder within this repository *(step_1, step_2, step 3)*. Each step folder includes:
2 subfolders: *notebooks* and *outputs*
2 text files detailing the full technical stack and a structured report
The *notebooks* folder contains executable code in Jupyter Notebook (.ipynb) format, while the *outputs* folder includes the resulting files generated from running the notebooks (CSV and JSON).

## Workflow overview
*Step 1*: Tag generation from text (NLP-based)
Retrieve metadata (titles, descriptions) from the Europeana API
Generate tags from the text using NLP (NER) with spaCy

*Step 2*: Tag generation from images (computer vision-based)
Download images from the dataset
Generate image captions using computer vision
Generate tags from the image captions

*Step 3*: Preparation for crowdsourcing (JSON-LD formatting)
Format all generated tags based on the W3C annotation model for direct ingestion in the crowdsourcing platform

# Applied heritage collection: The Krovets Ethnographic Collection
The Krovets ethnographic collection contains 3840 artefacts of Ukrainian traditional art and life spanning the 19th and 20th centuries. It is part of the Krovets Online Museum of Traditional Art of Ukraine (https://krovets.ua/en). The collection includes a variety of different artefacts, from everyday objects like utensils and clothing to folk art. 
The pilot focuses on the folk paintings subset of the Krovets collection, which contains 312 folk art paintings depicting scenes from everyday rural life and religious themes. In some cases, they depict historical figures (e.g. Taras Shevchenko). The artefacts were collected as part of a private initiative to preserve Ukrainian cultural heritage. 
The folk art paintings can be explored as a public gallery on Europeana: https://www.europeana.eu/en/galleries/26106-ukrainian-folk-art?page=4 

## Provenance
The institution providing the collection and metadata is the **Online Museum of the traditional art of Ukraine - KROVETS**. The aggregator gathering the content is **MUSEU**. The platform for accessing the collection is **Europeana**. 

## Technical Aspects




## Workflow Steps Overview

### Step 1: Text-based metadata enrichment
- Fetch structured metadata for the folk paintings dataset from the Europeana API
- Prepare the dataset for tag extraction through feature engineering
- Extract candidate tags from title and description using NLP (spaCy - NER)

### Step 2: Image enrichment
- Download images of folk paintings using their ids (fetched via the API)
- Generate captions for images using image recognition and machine vision
- Extract candidate tags from the machine-generated caption
