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

## Week 2 Work

The experiment index file is stored at `data/experiment_records/Experiment_Index.xlsx`. 
It links each experiment segment with the corresponding WiFi-CSI file, mmWave radar file, label information, and notes.

---

## Week 3 Work

### mmWave Sensor Data Collection Procedure

This project collects mmWave radar data for indoor human activity sensing. The main goal is to study whether human motion states can be distinguished using mmWave features such as distance, velocity, and reflection intensity.

### Activity Classes

The experiment includes the following activity classes:

| Code | Activity | Number of Segments |
|---|---|---:|
| C0 | Empty room | 20 |
| C1 | Single person static | 20 |
| C2 | Single person walking | 20 |
| C3 | Sit-to-stand | 20 |
| C4 | Hand waving / arm swinging | 20 |
| C5 | Multiple-person interference | Optional |

Each segment lasts about **10–20 seconds**.  
The basic dataset contains **100 mmWave segments** from C0 to C4.

### Sensor Setup

Before data collection, the mmWave radar should be fixed in a stable position. The sensor should face the human activity area directly. The recommended distance between the subject and the radar is **1–2 meters**, with **1.5 meters** used as the default distance.

The radar should not be moved during recording. Large metal objects, glass doors, and people passing through the background should be avoided when possible.

### Collection Steps

For each experiment segment, follow these steps:

1. Set up the mmWave radar and connect it to the computer.
2. Open the mmWave sensor software.
3. Load the radar configuration file.
4. Record the experiment information, including subject, action, distance, device position, and notes.
5. Start data recording.
6. Ask the subject to perform the assigned activity for 10–20 seconds.
7. Stop recording and save the mmWave data file.
8. Check whether the file was saved correctly.
9. Update the experiment record table.

### Data to Record

Each segment should have a corresponding record containing:

| Field | Description | Example |
|---|---|---|
| segment_id | Unique segment ID | S041 |
| subject | Subject ID | P01 |
| action | Activity code | C2 |
| action_name | Activity name | Single person walking |
| distance | Distance from radar | 1.5 m |
| device_position | Radar position | front |
| duration | Recording duration | 15 s |
| mmwave_file | Saved mmWave data file | mmwave_EXP001_S041_C2_P01_1p5m.csv |
| note | Additional notes | Normal walking, no interference |
| valid | Whether the segment is valid | yes |

### File Naming Rule

The recommended file naming format is:

```text
mmwave_<experiment_id>_<segment_id>_<action_code>_<subject_id>_<distance>.csv
```

## Notes

This repository is mainly used to keep all experiment data organized and easy to check.  
Each experiment should have clear file names, labels, and experiment records.

At this stage, the repository focuses on indoor human activity sensing as the initial data management and sensing-validation task for the SURF project.
