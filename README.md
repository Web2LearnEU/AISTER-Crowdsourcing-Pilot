![Alt text](https://web2learn.eu/wp-content/uploads/2026/03/banner-site.png)
<sub>*Folk Painting "Portrait of a girl" by unknown - Online Museum of the traditional art of Ukraine - KROVETS, Ukraine - CC BY-NC-ND. https://www.europeana.eu/en/item/1413/KYD1791*</sub>

# AISTER Human-In-The-Loop Crowdsourcing Pilot

*The repository contains the complete workflow and files for automatically generating description tags for artefacts on Europeana using AI tools (natural language processing, computer vision), and for running a human-in-the-loop crowdsourcing campaign to validate the tags.* 

##  Pilot description
This case study forms a small-scale exploratory pilot within the field of Digital Humanities / Cultural Heritage Informatics, operationalising and analysing a **human-in-the-loop (HITL) crowdsourcing framework for metadata enrichment in Europeana collections**. 

## Context
The pilot is part of the AISTER project, “AI-enabled Citizen Participation in University-driven Ukrainian Cultural Heritage Safeguarding”, under the Erasmus+ KA2, Higher Education sector programme. Learn more about the pilot project, the team, collaborating experts and partner institutions, and the workshops conducted: https://web2learn.eu/crowdsourcing-campaign-aister  

## Who can use the repository and how
The repository is designated as an open-source resource for digital humanities research, freely available for reproduction or reuse by scholars, students, and teachers. It is also intended for creative reuses.

## Repository description
The pilot consists of 3 technical steps, each documented in its respective folder within this repository *(step_1, step_2, step 3)*. Each step folder includes:
- 2 subfolders: *notebooks* and *outputs*
- 2 text files detailing the full technical stack and a structured report
The *notebooks* folder contains executable code in Jupyter Notebook (.ipynb) format, while the *outputs* folder includes the resulting files generated from running the notebooks (CSV and JSON).

## Workflow overview  
*Step 1*: Tag generation from text (NLP-based)  
- Retrieve metadata (titles, descriptions) from the Europeana API  
- Generate tags from the text using NLP (NER) with spaCy
  
*Step 2*: Tag generation from images (computer vision-based)  
- Download images from the dataset  
- Generate image captions using computer vision  
- Generate tags from the image captions
  
*Step 3*: Preparation for crowdsourcing (JSON-LD formatting)  
- Format all generated tags based on the W3C annotation model for direct ingestion in the crowdsourcing platform  

## Applied heritage collection: The Krovets ethnographic collection  
The Krovets ethnographic collection contains 3840 artefacts of Ukrainian traditional art and life spanning the 19th and 20th centuries. It is part of the Krovets Online Museum of Traditional Art of Ukraine (https://krovets.ua/en). The collection includes a variety of different artefacts, from everyday objects like utensils and clothing to folk art.  
The pilot focuses on the folk paintings subset of the Krovets collection, which contains 312 folk art paintings depicting scenes from everyday rural life and religious themes. In some cases, they depict historical figures (e.g. Taras Shevchenko). The artefacts were collected as part of a private initiative to preserve Ukrainian cultural heritage. 
The folk art paintings can be explored as a public gallery on Europeana: https://www.europeana.eu/en/galleries/26106-ukrainian-folk-art?page=4 

## Provenance
The institution providing the collection and metadata is the [Online Museum of the traditional art of Ukraine - KROVETS](https://krovets.ua/en). The aggregator gathering the content is [MUSEU](https://www.museuhub.eu/en/1/home). The platform for accessing the collection is [Europeana](https://www.europeana.eu/en). 

## Technical Aspects
…

The CSV file contains the following metadata:


…

## License    
This data repository is released under the [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0) licence. The Krovets ethnographic collection is published under a [CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/deed.en) licence. All accompanying metadata are released into the public domain using [CC0](https://creativecommons.org/public-domain/cc0/), to be freely copied, modified, distributed and reused. 

## Code of Conduct
The GitHub repository of Web2Learn follows the [Contributor Covenant](https://www.contributor-covenant.org/) to be overt in its openness, welcoming all people to engage and contribute, pledging in return to value them. To make our open communities welcoming, diverse, and inclusive, we are encouraging the adoption of a mindful code of conduct to express and share those values. Any unacceptable behaviour, such as trolling, insulting/derogatory comments, or personal or political attacks, will not be tolerated. The Contributor Covenant is released under the Creative Commons Attribution 4.0 International Public License.

## Project attribution
[Web2Learn](https://web2learn.eu/)  
[Mariana Ziku](https://web2learn.eu/mariana-ziku/): Researcher  
[Andreas Kouzelis](https://web2learn.eu/andreas-kouzelis/): Information Systems Εngineer  
[Andreas Darsaklis](https://web2learn.eu/andreas-darsaklis/): IT trainee  
[Dr Katerina Zourou](https://web2learn.eu/katerina-zourou/): Director

## Cite this dataset
When referring to or using the data repository in research publications and documentation, consider citing the dataset with its digital object identifier (DOI) minted on Zenodo. Citing the dataset of the HITL crowdsourcing pilot creates a mapping of attribution supporting efforts to release other datasets in the future. It also reduces the amount of "orphaned data," helping to retain source links.  
Cite the repository as: Ziku, M., Kouzelis, A., Darsaklis, A. & Zourou, K. (2026). The AISTER Human-In-The-Loop Crowdsourcing Pilot [Dataset]. Zenodo. 

## Acknowledgements
This README file follows the structure of the *KU Leuven Libraries* Git-based dataset documentation, i.e., https://github.com/KU-Leuven-Libraries/Portraits-Collection-Dataset. See: KU Leuven Libraries, Digitisation Department. (2019). The Portraits Collection Dataset of KU Leuven Libraries, Special Collections (Version 01-beta2) [Data set]. Zenodo. http://doi.org/10.5281/zenodo.3460785.  

The documentation of the Jupyter Notebooks follows the criteria of quality assessment for Jupyter projects by GLAM institutions, as published in Candela, G., Chambers, S., & Sherratt, T. (2023). An approach to assess the quality of Jupyter projects published by GLAM institutions. *Journal of the Association for Information Science and Technology*, 74(13), 1550–1564. https://doi.org/10.1002/asi.24835

## Disclaimer
Funded by the European Union. Views and opinions expressed are however those of the author(s) only and do not necessarily reflect those of the European Union or the European Education and Culture Executive Agency (EACEA). Neither the European Union nor EACEA can be held responsible for them.

