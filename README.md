![Alt text](https://web2learn.eu/wp-content/uploads/2026/03/banner-site.png)
<sub>*Folk Painting "Portrait of a girl" by unknown - Online Museum of the traditional art of Ukraine - KROVETS, Ukraine - CC BY-NC-ND. https://www.europeana.eu/en/item/1413/KYD1791*</sub>

# AISTER Human-In-The-Loop Crowdsourcing Pilot

*The repository contains the complete workflow, actionable code in notebooks and output files for:
1. Automatically generating annotations (description tags) for artefacts on **Europeana** using AI tools (natural language processing, computer vision) and Europeana APIs, and
2. Developing a human-in-the-loop crowdsourcing campaign on the **CrowdHeritage** platform to validate the annotations, also enabling participants to contribute additional user-generated annotations.  

##  Pilot description
This case study forms a small-scale exploratory pilot within the field of Digital Humanities / Cultural Heritage Informatics, operationalising and analysing a **human-in-the-loop (HITL) crowdsourcing framework for metadata enrichment in Europeana collections**. 

## Context
The pilot is part of the [AISTER project](https://aister.uni.lu/), “AI-enabled Citizen Participation in University-driven Ukrainian Cultural Heritage Safeguarding”, under the Erasmus+ KA2, Higher Education sector programme. Learn more about the pilot project, the team, collaborating experts and partner institutions, and the workshops conducted: https://web2learn.eu/crowdsourcing-campaign-aister  

## Who can use the repository and how
The repository is designated as an open-source resource for digital humanities research, freely available for reproduction or reuse by scholars, students, and teachers. It is also intended for creative reuses.

## Repository description
The pilot consists of 3 technical steps, each documented in its respective folder within this repository *(step_1, step_2, step 3)*. Each step folder includes:
- 2 subfolders: *notebooks* and *outputs*
- 2 text files detailing the full technical stack and a structured report
The *notebooks* folder contains executable code in Jupyter Notebook (.ipynb) format, while the *outputs* folder includes the resulting files generated from running the notebooks (CSV and JSON).

## Workflow overview  
*Step 1*: Annotation generation from text (NLP-based)  
- Retrieve metadata (titles, descriptions) from the Europeana API  
- Generate annotations from the text using NLP (NER) with spaCy
  
*Step 2*: Annotation generation from images (computer vision-based)  
- Download images from the dataset  
- Generate image captions using computer vision  
- Generate annotations from the image captions
  
*Step 3*: Preparation for crowdsourcing (JSON-LD formatting)  
- Format all generated annotations based on the W3C annotation model for direct ingestion in the crowdsourcing platform  

## Applied heritage collection: The Krovets ethnographic collection  
The Krovets ethnographic collection contains 3840 artefacts of Ukrainian traditional art and life spanning the 19th and 20th centuries. It is part of the Krovets Online Museum of Traditional Art of Ukraine (https://krovets.ua/en). The collection includes a variety of different artefacts, from everyday objects like utensils and clothing to folk art.  
The pilot focuses on the folk paintings subset of the Krovets collection, which contains 312 folk art paintings depicting scenes from everyday rural life and religious themes. In some cases, they depict historical figures (e.g. Taras Shevchenko). The artefacts were collected as part of a private initiative to preserve Ukrainian cultural heritage. 
The folk art paintings can be explored as a public gallery on Europeana: https://www.europeana.eu/en/galleries/26106-ukrainian-folk-art 

## Data Infrastructures and Provenance
The institution providing the ethnographic collection and metadata is the [Online Museum of the traditional art of Ukraine - KROVETS](https://krovets.ua/en). The aggregator gathering the content and metadata is [MUSEU](https://www.museuhub.eu/en/1/home). The platform for accessing the [collection of 3840 artefacts](https://www.europeana.eu/en/search?page=1&query=europeana_collectionName%3A%221413_KROVETS_Museum%22) and the [folk art subcollection gallery of 312 artefacts](https://www.europeana.eu/en/galleries/26106-ukrainian-folk-art) is [Europeana](https://www.europeana.eu/en). The platform for running the crowdsourcing campaign is [CrowdHeritage](https://crowdheritage.eu) maintained by [Datoptron](https://datoptron.com/).  
The pilot is developed by [Web2Learn](https://web2learn.eu), using [Google Colab/Jupyter Notebook](https://colab.research.google.com) for writing executable code, [GitHub](https://github.com/) for version control and code sharing, [Zenodo](https://zenodo.org/) open repository for long-term preservation of the dataset and related digital scholarship, and [Tableau](https://www.tableau.com/products/desktop) for data modelling and visual analytics.
5 crowdsourcing workshops and events in total are organised to perform human-in-the-loop tasks: 4 are organised by [Web2Learn](https://web2learn.eu), 3 online and 1 onsite at the Library of the University of Latvia, and 1 online workhsop is organised by [Young Folks](https://youngfolks.lv/eng) and the [Institute of Literature, Folklore and Art at the University of Latvia](https://www.lu.lv/en/about-us/structure/institutes/ul-institute-of-literature-folklore-and-art/). 

## Technical Aspects

### Step 1:
README for step 1: `step_1/README.md`
The `krovets_folk_metadata.csv` file contains metadata for the 312 records concerning folk paintings and icons retrieved using the Europeana API such as title, description, creator and image URL. The generated `krovets_folk_tags.csv` contains the NLP-generated tags (figures, objects, scenes) for each of the 312 records.

### Step 2:
README for step 2: `step_2/README.md`
The `captions.csv` file contains captions generated for each record using machine vision. The `tags.csv` file contains all candidate tags generated from the image caption (figures, objects, scenes, background, attire, text, damage).

### Step 3:
README for step 3: `step_3/README.md`
In step 3, there are **6 separate CSV files**, 5 capturing data from an event plus one combined csv file for all events. The files contain info about each user annotation, such as upvotes and downvotes and eventual approval or disapproval of the annotation depending on the difference between them.

In order to correctly display the CSV files and the registered records, it is suggested to use Libre or Open Office. The recommended setup for a properly display of the CSV file can be adjusted in the import popup window: 'Character set' to 'Unicode (UTF-8)', the separator options 'Tab', 'Comma' and 'Semicolon' should be selected and the 'Column type' of Column A (Record ID) should be changed from 'Standard' to 'Text'.

### Analytical information about each CSV file:
`KROVETS_FOLK_METADATA.CSV`
|Column name|Description|
|--|--|
|europeana_id|Item's id on Europeana|
|Title|Item's title|
|Description|A description about what is depicted in the record, materials, timespan, place of origin etc.|
|ImageLink|The item's image URL|
|Creator|Creator of the depicted artifact (if they're known)|
|Subject|Ethnographical region of origin & Item's category|
|Type of Item|Type of the depicted artefact (e.g. painting, clothing)|
|Medium|Materials used for crafting the item|
|Providing Institution|All items are provided by the [Online Museum of the traditional art of Ukraine - KROVETS](https://krovets.ua/en)|
|Aggregator|Items are gathered by [MUSEU](https://www.museuhub.eu/en/1/home)|
|Rights statement|Rights statement for each record|
|Creation date|Estimated timespan of the record (e.g. 20th century)|
|Places|Regions-oblasts where items originate from|
|Identifier|Record identifier on Europeana in the form of **/{collection_id}/{item_id}**|
|Is Part Of|All items are part of 1413_KROVETS_Museum|
|Providing Country|Country providing the record, in this case all items are from Ukraine|
|Collection Name|Same as Is Part Of|
|First time published on Europeana|Timestamp of when the item was first published on Europeana|
|Last time updated from providing institution|Timestamp of when the item was last updated on Europeana by its provider|

Metadata retrieved using the [Europeana API endpoint](https://api.europeana.eu/set/26106.json) for the specific set.

`KROVETS_FOLK_TAGS.CSV`
|Column name|Description|
|--|--|
|europeana_id|Item's id on Europeana|
|Figures|Persons that can be visibly seen in each painting|
|Objects|Items such as materials that are depicted|
|Scenes|Actions, context or anything in the background that is clearly depicted|

`CAPTIONS.CSV`
|Column name|Description|
|--|--|
|image_id|Id of the image's item|
|Caption|Caption generated for each painting through machine vision|

`TAGS.CSV`
|Column name|Description|
|--|--|
|image_id|Id of the image's item|
|figures|Person(s) visible on the image|
|objects|Items depicted on the image|
|scenes|Context of the image, scenery depicted|
|background|What can be seen in the background|
|attire|Clothing used by the persons depicted|
|text|Any text depicted on the painting|
|damage|Signs of damage on the artefact|

`*_UKRAINIAN-FOLKART-ANNOTATIONS.CSV`
|Column name|Description|
|--|--|
|created|Date of creation for the annotation|
|value|Tag evaluated|
|europeana_id|Id of the item possessing the tag|
|upvotes|Amount of upvotes by users|
|downvotes|Amount of downvotes by users|
|recommendation|**'accept'** if upvotes > downvotes else **'reject'** (or **'unknown'** if upvotes=downvotes)|
|event_number|The event in which the annotation was made (only in the combined csv file)|

The combined CSV holds a total of **18625** tag annotations from all 4 events.
For each event:
|CSV number|Tag annotation|
|--|--|
|1|4018|
|2|4018|
|3|4760|
|4|5829|

Tags generated in each step (not including human annotation)
|Step|Tags created|
|--|--|
|1|893|
|2|4581|
|Total|5474|

`ANNOTATIONS JSON FILES`
|Header name|Description|
|--|--|
|@context|Essential metadata for the json file|
|@graph|The body of the json file, holding the following info|

`BODY FROM JSON FILES`
|Header name|Description|
|--|--|
|type|'Annotation' in this case|
|created|Date of creation + hour|
|creator|Creator of the annotation (if recorded), usually an AI model|
|confidence|Value in range 0-1 about the confidence with which the tag annotation was made|
|body|Info about the content of the actual tag in question|
|target|The item's id on Europeana|
|review|Info about the amount of downvotes and upvotes the tag received and subsequent recommendation|

## License    
This data repository is released under the [Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0) licence. The Krovets ethnographic collection is published under a [CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/deed.en) licence. All accompanying metadata are released into the public domain using [CC0](https://creativecommons.org/public-domain/cc0/), to be freely copied, modified, distributed and reused. 

## Code of Conduct
The GitHub repository of Web2Learn follows the [Contributor Covenant](https://www.contributor-covenant.org/) to be overt in its openness, welcoming all people to engage and contribute, pledging in return to value them. To make our open communities welcoming, diverse, and inclusive, we are encouraging the adoption of a mindful code of conduct to express and share those values. Any unacceptable behaviour, such as trolling, insulting/derogatory comments, or personal or political attacks, will not be tolerated. The Contributor Covenant is released under the Creative Commons Attribution 4.0 International Public License.

## Project attribution
[Web2Learn](https://web2learn.eu/)  

[Mariana Ziku](https://web2learn.eu/mariana-ziku/): Lead Researcher  
[Andreas Kouzelis](https://web2learn.eu/andreas-kouzelis/): Information Systems Εngineer  
[Andreas Darsaklis](https://web2learn.eu/andreas-darsaklis/): IT trainee  
[Dr Katerina Zourou](https://web2learn.eu/katerina-zourou/): Director

## Cite this dataset
When referring to or using the data repository in research publications and documentation, cite the dataset using its digital object identifier (DOI) minted on Zenodo. Citing the dataset from the HITL crowdsourcing pilot creates a mapping of attribution that supports future efforts to release other datasets. It also reduces the amount of "orphaned data," helping to retain source links.  
Cite the repository as: Ziku, M., Kouzelis, A., Darsaklis, A. & Zourou, K. (2026). The AISTER Human-In-The-Loop Crowdsourcing Pilot [Dataset]. Zenodo. 

## Acknowledgements
This README file follows the structure of the *KU Leuven Libraries* Git-based dataset documentation, i.e., https://github.com/KU-Leuven-Libraries/Portraits-Collection-Dataset. See: KU Leuven Libraries, Digitisation Department. (2019). The Portraits Collection Dataset of KU Leuven Libraries, Special Collections (Version 01-beta2) [Data set]. Zenodo. http://doi.org/10.5281/zenodo.3460785.  

The documentation of the Jupyter Notebooks follows the criteria of quality assessment for Jupyter projects by GLAM institutions, as published in Candela, G., Chambers, S., & Sherratt, T. (2023). An approach to assess the quality of Jupyter projects published by GLAM institutions. *Journal of the Association for Information Science and Technology*, 74(13), 1550–1564. https://doi.org/10.1002/asi.24835

## Disclaimer
Funded by the European Union. Views and opinions expressed are however those of the author(s) only and do not necessarily reflect those of the European Union or the European Education and Culture Executive Agency (EACEA). Neither the European Union nor EACEA can be held responsible for them.

