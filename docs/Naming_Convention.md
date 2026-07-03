# Naming Convention

This document defines the file naming rules for the multi-modal sensing dataset.

The dataset includes two main data sources:

- WiFi-CSI data
- mmWave radar data

Each file name should include the device type, activity type, subject ID, distance, and trial number.

---

## File Name Format

```text
DEVICE_ACTION_SUBJECT_DISTANCE_TRIAL.extension
```

---

## Examples

```text
CSI_C1_S01_D2_T01.csv
MMW_C1_S01_D2_T01.csv
LABEL_C1_S01_D2_T01.xlsx
```

---

## Field Explanation

| Field | Example | Meaning |
|---|---|---|
| DEVICE | CSI | WiFi-CSI data |
| DEVICE | MMW | mmWave radar data |
| DEVICE | LABEL | Label file |
| ACTION | C1 | Activity code |
| SUBJECT | S01 | Subject ID |
| DISTANCE | D2 | Distance is 2 meters |
| TRIAL | T01 | Trial number 1 |

---

## Device Code

| Code | Meaning |
|---|---|
| CSI | WiFi-CSI data |
| MMW | mmWave radar data |
| LABEL | Label file |

---

## Activity Code

| Code | Activity |
|---|---|
| C0 | Empty Room |
| C1 | Standing |
| C2 | Walking |
| C3 | Sit-Stand |
| C4 | Hand Wave |
| C5 | Multiple People |

---

## Naming Rules

- Use uppercase letters in file names.
- Use `_` to separate different fields.
- Do not use spaces in file names.
- Keep the same ACTION, SUBJECT, DISTANCE, and TRIAL for matching CSI, MMW, and LABEL files.
- File names should be consistent with `experiment_records.xlsx`.

---

## Example of Matching Files

For one experiment of subject S01 standing at 2 meters, trial 1:

```text
CSI_C1_S01_D2_T01.csv
MMW_C1_S01_D2_T01.csv
LABEL_C1_S01_D2_T01.xlsx
```

These three files should refer to the same experiment.
