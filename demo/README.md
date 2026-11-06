# Demo: one painting through the pipeline

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Web2LearnEU/AISTER-Crowdsourcing-Pilot/blob/main/demo/aister_one_painting.ipynb)

`aister_one_painting.ipynb` runs the four steps of the pilot on a single painting from the Europeana gallery [Ukrainian folk art](https://www.europeana.eu/en/galleries/26106-ukrainian-folk-art): text tags with spaCy, image tags with the Qwen models, the crowd's decisions from the published dataset, and the DE-BIAS check. It reuses the code, models and prompts of the notebooks in `step_1` to `step_4`, which process the whole collection in batches.

The saved outputs show a run on painting KYD1855.

**Requirements**
- Google Colab with a GPU runtime (a free T4 is enough). The two models download about 13.5 GB on first run.
- A free Europeana API key, stored in Colab Secrets as `EUROPEANA_API_KEY` (request one at [europeana.eu/account/api-keys](https://www.europeana.eu/account/api-keys)).
- Optional: a Hugging Face token as `HF_TOKEN`, for faster model downloads.
