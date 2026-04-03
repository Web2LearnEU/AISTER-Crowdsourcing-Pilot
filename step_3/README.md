# Step 3 - Crowdsourcing annotation exports

Step 3 turns **Web Annotation** JSON exports from the Ukrainian folk art crowdsourcing campaign into **tabular CSVs** for analysis, and can **merge** several event exports into one file with votes aggregated per object and label.

## Notebooks


| Notebook                                           | Purpose                                                                                                                                                                    |
| -------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `notebooks/step_3-01_create_annotations_csv.ipynb` | Read a JSON export (`@graph`), normalize fields (`europeana_id`, `value`, votes, `recommendation`), and write one CSV per export.                                          |
| `notebooks/step_3-02_combine_annotations.ipynb`    | Load multiple per-event CSVs from `outputs/`, merge on `(europeana_id, value)`, sum votes, recompute `recommendation`, write `combined_ukrainian-folkart-annotations.csv`. |


## Layout

```text
step_3/
  data/
    *_ukrainian-folkart_annotations.json   # Web Annotation exports (input)
  notebooks/
    step_3-01_create_annotations_csv.ipynb
    step_3-02_combine_annotations.ipynb
  outputs/
    *_ukrainian-folkart-annotations.csv     # one CSV per export / event
    combined_ukrainian-folkart-annotations.csv   # merged across events
```

## Usage

- Run in **Google Colab** or **local Jupyter** with `pandas` installed. Each notebook has a short setup cell for `BASE_DIR` (and optional Drive mount in Colab).
- Point `INPUT_JSON` / `INPUT_CSVS` at the files you need; filenames follow the `1_…`, `2_…` convention for separate campaign exports.

