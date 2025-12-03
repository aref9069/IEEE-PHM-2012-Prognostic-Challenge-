# IEEE-PHM-2012-Prognostic-Challenge
This repository contains the dataset from the PHM IEEE 2012 Data Challenge, previously hosted on the FEMTO-ST website but no longer available online. It includes vibration data from six training bearings under three operating conditions and eleven test bearings. Additional details are provided in the included PDF.


⭐ Overview

This repository contains the IEEE PHM 2012 Prognostics Challenge dataset — a widely used benchmark for bearing degradation and Remaining Useful Life (RUL) estimation. The challenge focuses on predicting the life duration of ball bearings undergoing realistic degradation under controlled laboratory conditions on the PRONOSTIA test platform


The dataset includes run-to-failure vibration and temperature recordings, collected under three different loading conditions. Participants were originally asked to build prognostic models using 6 complete degradation experiments and estimate RUL for 11 truncated test experiments.

PRONOSTIA Experiment Platform

According to the challenge documentation (see pages 2–5 of the PDF), the PRONOSTIA test rig consists of:

1. Rotating Part

250 W AC motor + gearbox (up to ~2000 rpm)

Bearing support shaft with pillow blocks

Incremental encoder for rotation speed measurement

2. Loading Part

Pneumatic jack applying radial force up to the bearing’s maximum dynamic load (4000 N)

Lever arm for force amplification

Force sensor for real-time monitoring

3. Measurement Part

Two DYTRAN 3035B miniature accelerometers (horizontal + vertical axes)

PT100 RTD temperature probe

Sampling characteristics:

  Vibration: 25.6 kHz, 2560 samples every 10 s
  
  Temperature: 10 Hz, 600 samples per minute


📂 Dataset Contents

The experiments include run-to-failure data for bearings operating under:

| Condition | Speed (rpm) | Load (N) |
| --------- | ----------- | -------- |
| **1**     | 1800        | 4000     |
| **2**     | 1650        | 4200     |
| **3**     | 1500        | 5000     |



Training Set (6 bearings)

Full run-to-failure vibration + temperature signals used to build prognostic models.

Test Set (11 bearings)

Truncated at an unknown degradation point.
Your task: Predict the RUL until the vibration amplitude exceeds 20 g, the failure threshold used in the challenge.


Actual RULs are provided on page 8 of the PDF.
All data files follow this structure:
acc_xxxxx.csv   # Vibration - horizontal & vertical channels
temp_xxxxx.csv  # Temperature data



Each vibration file contains:
| Column | Description                       |
| ------ | --------------------------------- |
| 1–4    | Timestamp (hour/min/sec/microsec) |
| 5      | Horizontal acceleration           |
| 6      | Vertical acceleration             |



🎯 Purpose of This Repository

This repo makes the dataset easily accessible for:

Remaining Useful Life (RUL) prediction

Signal processing (FFT, time/frequency analysis)

Wavelet-based health indicators

Machine learning & deep learning benchmarking

Condition monitoring research

📊 Why This Dataset Is Important

Bearings cause 40–50% of industrial motor failures.

Run-to-failure experiments offer realistic degradation patterns, unlike synthetic seeded-fault datasets.

The data includes high variability in life durations (from 1 to 7 hours), creating a challenging benchmark.

Traditional fault-frequency models (BPFI/BPFO) do not apply, since degradation affects multiple components simultaneously (noted in PDF, page 6)

🔍 Applications

Researchers use this dataset to develop and test:

Data-driven prognostic models (ANN, LSTM/GRU, CNN, TCN, Transformers)

Hybrid signal processing + ML pipelines

Health index extraction

RUL regression models

Early-fault detection and anomaly detection systems

Feature engineering (e.g., RMS, kurtosis, envelope spectrum, WPT features)

🏆 Original Challenge Outcome

Top performers included:

A.L.D. Ltd. (Industry winner)

University of Maryland CALCE (Academic winner)

Scoring was based on percent error with different penalties for overestimation vs. underestimation (page 7)

📑 Citation

Please cite the original dataset authors:

Patrick Nectoux, Rafael Gouriveau, Kamal Medjaher, Emmanuel Ramasso, Brigitte Morello, Noureddine Zerhouni, Christophe Varnier.
PRONOSTIA: An Experimental Platform for Bearings Accelerated Life Test.
IEEE PHM Conference, Denver, CO, USA, 2012.
(Dataset source: IEEE PHM 2012 Data Challenge)


📎 License

The dataset is publicly available for research as per the challenge organizers.
This repository merely redistributes it for accessibility and scientific reproducibility.


