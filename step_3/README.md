# Step 3 - Export crowdsourcing annotations (JSON → CSV)

Convert **Web Annotation** JSON exports from the Ukrainian folk art crowdsourcing campaign into an analysis-ready **CSV**.

Event exports are cumulative snapshots. Later events already include earlier votes, so the latest event export contains the full vote set.

## Layout

```text
step_3/
  data/
    *_ukrainian-folkart_annotations.json   # event export JSON files (e.g. 1_..., 2_..., 3_...)
  notebooks/
    step_3-01_create_annotations_csv.ipynb  # JSON → CSV
    step_3-02_combine_annotations.ipynb     # Creates a combined CSV for all 4 events
  outputs/
    *_ukrainian-folkart-annotations.csv     # one CSV per event export (e.g. 1_..., 2_..., 3_...)
    ukrainian-folkart-annotations.csv       # a combined CSV for all event exports (1,2,3,4)
```

## Usage of notebooks
`notebooks/step_3-01_create_annotations_csv.ipynb` / `notebooks/step_3-02_combine_annotations.ipynb`
- Open the file in **Google Colab** or **local Jupyter** (requires `pandas`).
- In the setup cell, set `BASE_DIR` to your local repo path (or mount Drive in Colab).
- Set `INPUT_JSON` to the export you want to convert (typically the latest event, e.g. `data/4_ukrainian-folkart_annotations.json`) if running the first notebook. Otherwise if you use the second notebook you do not need to specify input paths.
- Run all cells to write the CSV into `outputs/` (e.g. `outputs/4_ukrainian-folkart-annotations.csv` or `outputs/ukrainian-folkart-annotations.csv` if running the second notebook).
