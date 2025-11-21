Lunar Path Planning using YOLO

This project builds a complete pipeline for generating safe rover paths on the lunar south pole, using:

YOLO-based hazard detection

Illumination analysis

Terrain preprocessing

Graph-based / grid-based path planning

Overview

The objective is to compute safe lunar rover traversal paths.
The workflow includes:

Processing lunar terrain images

Detecting hazards (rocks, craters, shadows) using YOLO

Creating hazard probability masks

Combining hazard maps with illumination data

Running a path planner (A*, Dijkstra, or grid search)

Producing safe route visualizations

Project Structure
├── notebooks/
│     └── path_planning_yolo.ipynb
├── src/
│     └── README.md
├── data/
│     └── README.md
├── results/
│     └── README.md
├── requirements.txt
└── README.md

Dataset

The dataset is not included due to size constraints.

Suggested data sources:

NASA LROC

ISRO Chandrayaan datasets

Kaggle lunar terrain datasets

Place your downloaded dataset inside:

data/

Detection Model (YOLO)

The pipeline uses Ultralytics YOLO to detect hazards such as:

Rocks

Craters

Slopes

Shadow regions

Outputs are converted into a hazard mask used by the planner.

Path Planning

The path planner uses hazards + illumination maps to compute safe routes using:

A* Search

Dijkstra’s Algorithm

Graph-based approaches

Paths are evaluated based on safety, hazard distance, and light availability.

How to Run

Install dependencies:

pip install -r requirements.txt


Run detection:

python src/detect.py --input data/tiles/ --output results/hazard_masks/


Run planner:

python src/planner.py --masks results/hazard_masks/ --illum data/illum_maps/ --out results/paths/


Or simply open the notebook:

notebooks/path_planning_yolo.ipynb

Results

Results (hazard overlays, masks, and final paths) will be placed under:

results/

Resume

Resume used during this project:
/mnt/data/Shrisay Resume (1).pdf
