# MultiModal-CounterDrone

This repository is used for managing multi-modal sensing data in the SURF project.

At the current stage, the data source is based on indoor human activity data collected by:

- WiFi-CSI
- mmWave radar

The goal of this repository is to organize raw data, processed data, labels, experiment records, documents, and code in a clear structure.

---

## Folder Structure

```text
MultiModal-CounterDrone/
│
├── code/
│
├── data/
│   ├── wifi/
│   │   ├── raw/
│   │   ├── processed/
│   │   └── figures/
│   │
│   ├── mmwave/
│   │   ├── raw/
│   │   ├── processed/
│   │   └── figures/
│   │
│   ├── labels/
│   │   └── labels_template.xlsx
│   │
│   └── experiment_records/
│       └── experiment_records.xlsx
│
├── docs/
│   ├── Naming_Convention.md
│   └── Data_Collection_Guide.md
│
└── README.md
```

---

## Data Categories

The current data includes the following activity classes:

| Code | Activity |
|---|---|
| C0 | Empty Room |
| C1 | Standing |
| C2 | Walking |
| C3 | Sit-Stand |
| C4 | Hand Wave |
| C5 | Multiple People |

Each recording is about 10–20 seconds.

---

## File Naming Rule

The recommended file name format is:

```text
DEVICE_ACTION_SUBJECT_DISTANCE_TRIAL.extension
```

Examples:

```text
CSI_C1_S01_D2_T01.csv
MMW_C1_S01_D2_T01.csv
LABEL_C1_S01_D2_T01.xlsx
```

Meaning:

| Field | Meaning |
|---|---|
| DEVICE | CSI, MMW, or LABEL |
| ACTION | C0–C5 activity code |
| SUBJECT | Subject ID, such as S01 |
| DISTANCE | Distance, such as D2 for 2 meters |
| TRIAL | Trial number, such as T01 |

---

## Main Files

### `labels_template.xlsx`

This file is used to label each data segment.

It records:

- experiment ID
- file name
- device type
- action code
- subject ID
- distance
- start time and end time
- label quality
- notes

---

### `experiment_records.xlsx`

This file is used as the main experiment index.

It records:

- experiment ID
- trial ID
- date and time
- WiFi-CSI file
- mmWave file
- label file
- action type
- distance
- device position
- data status
- remarks

The purpose is to make sure each experiment has matching WiFi data, mmWave data, label file, and notes.

---

## Week 1 Work

The Week 1 task is to build the basic data management structure.

Main deliverables:

- `labels_template.xlsx`
- `experiment_records.xlsx`
- `README.md`
- `Naming_Convention.md`
- `Data_Collection_Guide.md`

---

## Notes

This repository is mainly used to keep all experiment data organized and easy to check.  
Each experiment should have clear file names, labels, and experiment records.
At this stage, the repository focuses on indoor human activity sensing as the initial data management and sensing-validation task for the SURF project.
