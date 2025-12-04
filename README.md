# Social Media Content Intelligence

This project implements an end-to-end pipeline for analyzing, categorizing, captioning, moderating, and recommending social media image/video content.

It produces the required deliverables:

- **categories.csv** — Predicted category for each file  
- **captions_tags.json** — Auto-generated captions & tags  
- **moderation_model.ipynb** — Safe/unsafe content detection  
- **recommendation.ipynb** — Similar content recommendations  
- **engagement_model.ipynb** (optional) — Engagement prediction  
- **metadata.json / metadata.csv** — Extracted metadata  

---

## Features

### 1. Embedding Extraction
Deep CNN/Transformer embeddings for every image/video frame.

### 2. Content Categorization
- KMeans clustering  
- Outputs: `categories.csv`, `clustering_summary.json`, `cluster_gallery/`

### 3. Caption & Tag Generation
- BLIP / ViT-GPT2 captioning  
- Outputs: `captions_tags.json`

### 4. Content Moderation
- Simulated labels per assignment  
- Lightweight classifier  
- Outputs: `moderation.json`, `moderation_model.ipynb`

### 5. Recommendation Engine
- Cosine similarity on embeddings  
- Output: `recommendation.json`, `recommendation.ipynb`

### 6. Metadata Extraction
- File-level metadata  
- Outputs: `metadata.json`, `metadata.csv`

---

## Repository Structure

scripts/ # All Python scripts for each step
models/ # Saved models (moderation, clustering centers)
outputs/ # Final deliverables
notebooks/ # Jupyter notebooks (moderation, recommendation)
app/ # Optional demo interface
README.md
requirements.txt

---

## How to Run

### Install dependencies
pip install -r requirements.txt

shell
Copy code

### Run pipeline (optional)
python scripts/extract_embeddings.py
python scripts/cluster_embeddings.py
python scripts/generate_captions_vitgpt2.py
python scripts/simulate_moderation_labels.py
python scripts/train_moderation.py
python scripts/recommendation_engine.py

shell
Copy code

### View Cluster Gallery
open outputs/cluster_gallery/index.html

---

## Deliverables Included

| File | Description |
|------|-------------|
| **categories.csv** | Predicted content category |
| **captions_tags.json** | Generated captions + tags |
| **moderation_model.ipynb** | Safe/unsafe detection model |
| **recommendation.ipynb** | Similar-content recommendations |
| **engagement_model.ipynb** | Optional engagement predictor |
| **metadata.json / metadata.csv** | Source metadata summary |
| **cluster_gallery/** | Visual HTML gallery of clusters |

---

## Notes
- Dataset not included due to size; pipeline supports any local image/video folder.
- Moderation labels are simulated as specified in the assignment.
- Occasional numeric warnings during matrix operations do not affect outputs.
