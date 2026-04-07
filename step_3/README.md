# Step 3 - Crowdsourcing annotation exports

Step 3 turns **Web Annotation** JSON exports from the Ukrainian folk art crowdsourcing campaign into **tabular CSVs** for analysis.

Event exports are **incremental snapshots**: each later event already includes prior votes. In practice, the 4th event export contains all votes from events 1-4.

## Notebooks

- `notebooks/step_3-01_create_annotations_csv.ipynb`: Read a JSON export (`@graph`), normalize fields (`europeana_id`, `value`, votes, `recommendation`), and write one CSV export.
- `notebooks/step_3-02_event_stats.ipynb`: Read all per-event CSV exports from `outputs/` and compute event-level summary stats.

## Layout

```text
step_3/
  data/
    *_ukrainian-folkart_annotations.json   # Web Annotation exports (input)
  notebooks/
    step_3-01_create_annotations_csv.ipynb
    step_3-02_event_stats.ipynb
  outputs/
    *_ukrainian-folkart-annotations.csv     # one CSV per export / event
```

## Usage

- Run in **Google Colab** or **local Jupyter** with `pandas` installed. Both notebooks include a short setup cell for `BASE_DIR` (and optional Drive mount in Colab).
- Use `step_3-01_create_annotations_csv.ipynb` to convert a JSON export (`INPUT_JSON`) into CSV.
- Use `step_3-02_event_stats.ipynb` to summarize all event CSVs in `outputs/`.

