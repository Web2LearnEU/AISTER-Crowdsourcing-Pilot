# Step 2 - Image Enrichment Pipeline

Step 2 enriches the Krovets folk paintings and icons subset with:

- image captions generated from each image
- structured candidate tags extracted from those captions

This stage processes 312 records and produces machine-generated metadata that is later reviewed by experts in Step 3 (human-in-the-loop).

## Overview

The pipeline uses a two-stage approach:

1. **Caption generation (vision-language model)**  
   `notebooks/02_image_captioning.ipynb`
2. **Tag extraction (text-only language model)**  
   `notebooks/03_tag_extraction.ipynb`

Main model choices used in experiments:

- **Captioning:** `Qwen3-VL-2B-Instruct`
- **Tag extraction:** `Qwen3.5-4B`

## Repository Structure

```text
step_2/
  data/
    folk_images/                        # input image files (downloaded locally)
  notebooks/
    01_download_images_from_collection.ipynb
    02_image_captioning.ipynb
    03_tag_extraction.ipynb
  outputs/
    captions.csv                        # generated captions per image
    tags.csv                            # generated candidate tags per image
```

## Inputs and Outputs

### Inputs

- 312 folk painting/icon image files in `data/folk_images/`
- Europeana collection item IDs and metadata retrieved from
  `https://api.europeana.eu/set/26106.json` (used to resolve item records and
  image URLs)

### Outputs

- `outputs/captions.csv`  
  One row per image with at least: `image_id`, `caption`

- `outputs/tags.csv`  
  Candidate tags for categories:
  `Figures`, `Attire`, `Objects`, `Background`, `Scenes`, `Text`, `Damage`

## Usage

You can run this workflow in **Google Colab** or in a **local Jupyter environment**.

### 1) Prepare environment

- Python 3.10+ recommended
- Install notebook dependencies used in the notebooks (transformers, torch,
  pandas, and related packages)
- Configure access to model providers if required (for example, Hugging Face)

### 2) Download / prepare images from Europeana API

Run:

- `notebooks/01_download_images_from_collection.ipynb`

This notebook:

- fetches collection items from Europeana Set API: `https://api.europeana.eu/set/26106.json`
- fetches record-level details from Europeana Record API:
  `https://api.europeana.eu/record/v2/1413/{item_id}.json`
- extracts provider image URLs and downloads images using multi-threading

API authentication notes:

- Create a Europeana account and generate an API key
- In Colab, save the key in Secrets as `EUROPEANA_API_KEY`
- Requests use API key in headers as `X-API-KEY` (not query parameter)

Confirm downloaded images are available locally under `data/folk_images/`
(or your mapped drive folder if running in Colab).

### 3) Generate captions

Run:

- `notebooks/02_image_captioning.ipynb`

Expected output:

- `outputs/captions.csv`

### 4) Extract tags

Run:

- `notebooks/03_tag_extraction.ipynb`

Input to this notebook:

- `outputs/captions.csv` (generated in Step 3 above)

Expected output:

- `outputs/tags.csv`


## Limitations

- Captions and tags are **AI-generated suggestions**, not final annotations.
- Captions may occasionally include speculative or incorrect cultural labeling
  (for example, "traditional Russian folk attire" or "Russian Orthodox
  monastery complex"), even when the material is Ukrainian.
- Tags are often general ("man", "woman") and may miss specific named entities
  (for example, a depicted person such as "Taras Shevchenko").
- Some extracted tags are full phrases/sentences (for example, "older man in
  light blue shirt" or "visible signs of age and wear") rather than concise
  normalized terms.