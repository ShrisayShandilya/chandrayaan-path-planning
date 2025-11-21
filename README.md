# Lunar Path Planning using YOLO

This project builds a complete pipeline for generating safe rover paths on the **lunar south pole**, using:

- YOLO-based hazard detection  
- Illumination analysis  
- Terrain preprocessing  
- Graph-based / grid-based path planning  

---

## Overview

The objective is to compute safe lunar rover traversal paths. The workflow includes:

1. Processing lunar terrain images  
2. Detecting hazards (rocks, craters, shadows) using YOLO  
3. Creating hazard probability masks  
4. Combining hazard maps with illumination data  
5. Running a path planner (A*, Dijkstra, or grid search)  
6. Producing safe route visualizations  

---

## Project Structure

```
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
```

---

## Dataset

The dataset is **not included** due to size constraints. Suggested sources:

- NASA LROC  
- ISRO Chandrayaan datasets  
- Kaggle lunar terrain datasets  

Place your downloaded dataset inside:

```
data/
```

---

## Detection Model (YOLO)

The pipeline uses **Ultralytics YOLO** to detect hazards such as:

- Rocks  
- Craters  
- Slopes  
- Shadow regions  

Outputs are converted into a hazard mask used by the planner.

---

## Path Planning

The path planner uses hazard maps + illumination maps to compute safe routes using:

- A* Search  
- Dijkstra’s Algorithm  
- Graph-based approaches  

Paths are scored based on:

- Safety  
- Hazard distance  
- Illumination  
- Traversal cost  

---

## How to Run

Install dependencies:

```
pip install -r requirements.txt
```

Run detection:

```
python src/detect.py --input data/tiles/ --output results/hazard_masks/
```

Run the planner:

```
python src/planner.py --masks results/hazard_masks/ --illum data/illum_maps/ --out results/paths/
```

Or open the notebook:

```
notebooks/path_planning_yolo.ipynb
```

---

## Results

Generated visualizations will be stored under:

```
results/
```

---

## Resume

Resume used during this project:  
`/mnt/data/Shrisay Resume (1).pdf`
