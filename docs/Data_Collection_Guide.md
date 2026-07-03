# Data Collection Guide

This document explains the basic rules for collecting and recording data.

The current dataset is based on indoor human activity data collected by WiFi-CSI and mmWave radar.

---

## Data Sources

The data should be collected from:

- WiFi-CSI device
- mmWave radar device

Each experiment should record both WiFi-CSI data and mmWave radar data if possible.

---

## Activity Classes

| Code | Activity |
|---|---|
| C0 | Empty Room |
| C1 | Standing |
| C2 | Walking |
| C3 | Sit-Stand |
| C4 | Hand Wave |
| C5 | Multiple People |

---

## Recording Rules

Each recording should follow these rules:

- Each recording lasts about 10–20 seconds.
- The subject should perform one activity during one recording.
- The distance between the subject and device should be recorded.
- The device position should be recorded.
- Any problem during the experiment should be written in the notes.

---

## Required Information

For each experiment, record the following information:

| Item | Example |
|---|---|
| Experiment ID | EXP001 |
| Trial ID | T01 |
| Activity Code | C2 |
| Subject ID | S01 |
| Distance | 2 m |
| Device Position | Front |
| WiFi-CSI File | CSI_C2_S01_D2_T01.csv |
| mmWave File | MMW_C2_S01_D2_T01.csv |
| Label File | LABEL_C2_S01_D2_T01.xlsx |
| Operator | Shang Weipeng |
| Remark | Normal recording |

---

## Data Storage

Save the files in the correct folders:

```text
data/wifi/raw/
data/mmwave/raw/
data/labels/
data/experiment_records/
```

Example:

```text
data/wifi/raw/CSI_C2_S01_D2_T01.csv
data/mmwave/raw/MMW_C2_S01_D2_T01.csv
data/labels/LABEL_C2_S01_D2_T01.xlsx
```

---

## Experiment Record

After each experiment, update:

```text
data/experiment_records/experiment_records.xlsx
```

The experiment record should include:

- experiment ID
- trial ID
- date
- activity code
- subject ID
- distance
- WiFi-CSI file name
- mmWave file name
- label file name
- data status
- remarks

---

## Label File

The label file should be saved in:

```text
data/labels/
```

The label file should record:

- source file
- device type
- action code
- action name
- subject ID
- distance
- start time
- end time
- label quality
- label note

---

## Data Checking

Before uploading data to GitHub, check:

- The file name follows the naming convention.
- The WiFi-CSI file is saved correctly.
- The mmWave file is saved correctly.
- The label file is saved correctly.
- The experiment is recorded in `experiment_records.xlsx`.
- The action code is correct.
- Any problem is written in the remark column.

---

## Notes

The purpose of this guide is to make sure all collected data is clear, organized, and easy to use for later analysis.
