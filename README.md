# AISTER Human-In-The-Loop Crowdsourcing Pilot

##  Case study description
This case study forms a small-scale exploratory pilot within the field of Digital Humanities / Cultural Heritage Informatics, operationalising and analysing a **human-in-the-loop (HITL) crowdsourcing framework for metadata enrichment in Europeana collections**. 

## GitHub repository description
The repository contains the complete workflow and files for automatically generating description tags for artefacts using AI tools (natural language processing, computer vision), and for running a human-in-the-loop crowdsourcing campaign to validate the tags. 

## Context
The pilot is part of the AISTER project, “AI-enabled Citizen Participation in University-driven Ukrainian Cultural Heritage Safeguarding”, under the Erasmus+ KA2, Higher Education sector programme. Learn more about the pilot project, the team, collaborating experts and partner institutions, and the workshops conducted: https://web2learn.eu/crowdsourcing-campaign-aister 

## Who can use the repository and how
The repository is designated as an open-source resource for digital humanities research, freely available for reproduction or reuse by scholars, students, and teachers. It is also intended for creative reuses.



## Workflow Steps Overview

### Step 1: Text-based metadata enrichment
- Fetch structured metadata for the folk paintings dataset from the Europeana API
- Prepare the dataset for tag extraction through feature engineering
- Extract candidate tags from title and description using NLP (spaCy - NER)

### Step 2: Image enrichment
- Download images of folk paintings using their ids (fetched via the API)
- Generate captions for images using image recognition and machine vision
- Extract candidate tags from the machine-generated caption
