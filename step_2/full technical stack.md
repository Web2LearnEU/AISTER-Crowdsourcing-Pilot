# Full Technical Stack

Fill in all components of software tools, programming languages, platforms, libraries, and AI systems used to develop, analyse, and implement the project’s technical implementation.

## STEP 2 – Image-based Analysis

### Programming Language
- Python 3

### Execution Environments
- Local development environment (Linux)
- Google Colab (notebook runtime)
- Google Drive (mounted storage for input/output files)

### Libraries and Frameworks
- `pandas` (tabular data processing, CSV handling)
- `torch` / PyTorch (model inference, device handling)
- `transformers` (Hugging Face model loading, tokenization, generation)
- `accelerate` (efficient model execution on available hardware)
- `bitsandbytes` (4-bit/8-bit quantization for Stage 2 model loading)
- `Pillow` / `PIL` (image loading and preprocessing)
- `matplotlib` (image preview and quick visual checks)
- Python standard library:
  - `pathlib`
  - `typing`
  - `time`
  - `csv`
  - `json`
- `google.colab` (Drive mounting and Colab-specific integration)

### Data Sources
- Images from Europeana (Krovets collection records), accessed through the Europeana User Set API

### Data Formats
- Images: JPEG (`.jpg`)
- Intermediate and output tables: CSV (`.csv`)
- Spreadsheet exchange: XLSX / Google Sheets

### AI Systems
- `Qwen3-VL-2B-Instruct` (image captioning)
- `Qwen3.5-4B` (tag extraction from generated captions)

### Outputs
- Enriched spreadsheet containing:
  - generated image captions
  - normalized tags
  - category fields
