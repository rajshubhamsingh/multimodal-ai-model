## Multimodal AI Captioning Pipeline
From Demo to Scalable System — Generate and rank image captions using BLIP & CLIP, ready for production.

## 📌 Overview
This project implements a scalable multimodal AI pipeline for image caption generation and ranking.
It started as a Colab prototype and has been refactored into modular Python scripts with a configuration file, batch processing, and exportable evaluation reports.

The pipeline can:

Generate multiple candidate captions for each image using BLIP

Rank captions using CLIP

Export results to CSV for human-in-the-loop evaluation

Apply decision rules for auto-publish / review / flag

Scale to large datasets with FAISS-based retrieval

## ✨ Features
Modular design — reusable Python modules (caption_generator.py, caption_ranker.py, etc.)

Configurable — set parameters in config.yaml

Batch processing — handle 10x or 100x more images

Human evaluation export — outputs/human_eval.csv

Scalable search — FAISS for fast similarity queries

## Deployment-ready — can be wrapped into FastAPI / Streamlit

Automatable — run weekly via cron, GitHub Actions, or Airflow

## 📂 Project Structure
bash
Copy
Edit
.
├── config.yaml                # Pipeline configuration
├── run_pipeline.py            # Entry point for batch runs
├── image_loader.py            # Image loading (local & URL)
├── caption_generator.py       # BLIP-based caption generation
├── caption_ranker.py          # CLIP-based caption ranking
├── evaluation.py              # CSV export for human eval
├── utils.py                   # Common utilities
├── images/                    # Input images
├── outputs/                   # Generated captions & CSVs
└── requirements.txt           # Dependencies

## 🚀 Quick Start
1️⃣ Install dependencies
bash
Copy
Edit
pip install -r requirements.txt
2️⃣ Add images
Place your .jpg, .png, .jpeg, or .webp files in the images/ directory.

3️⃣ Run the pipeline
bash
Copy
Edit
python run_pipeline.py
4️⃣ Check the results
Captions and rankings will be saved to:

bash
Copy
Edit
outputs/human_eval.csv
⚙ Configuration
Modify config.yaml to set:

Model names (BLIP / CLIP variants)

Input image directory

Output CSV location

Number of captions to generate (generate_n)

Top-K captions to keep (top_k)

Example:

yaml
Copy
Edit
pipeline:
  generate_n: 5
  top_k: 5
📊 Turning Data into Action
This pipeline is built for decision-making, not just demos.
Example usage:

Auto-publish captions when score ≥ 0.7

Route to review if score between 0.5–0.7

Flag for manual writing if score < 0.5 or contains sensitive terms

You can integrate these rules in run_pipeline.py.

## 📈 Scaling Up
Batch size control in config.yaml

FAISS indexing for millions of captions

Schedule weekly runs with cron jobs, GitHub Actions, or Airflow

## 🖥 Deployment
Possible deployment options:

FastAPI REST API for on-demand captioning

Streamlit / Gradio app for interactive demos

Hugging Face Spaces for public sharing

Docker container for cloud deployment

## 🤝 Contributing
Contributions are welcome!
Please:

Fork the repo

Create a feature branch

Submit a pull request

📬 Contact
Shubham Kumar Singh
📧 Email: sk7892990@gmail.com
💼 LinkedIn: https://www.linkedin.com/in/shubham-kumar-singh-001651271/

🐙 GitHub: https://github.com/rajshubhamsingh
    
