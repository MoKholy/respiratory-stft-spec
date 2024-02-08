# Classification of Sleep Apnea using STFT-Spectrograms of Chest Respiratory movement signals. 

This repository contains the files used to read the signal files of the APNEA-ECG database, generate STFT-spectrograms of the signals, and a simple CNN model used to classify the Spectrograms according to presence of Apnea events in patients. 

# Dataset

The dataset used was the APNEA-ECG database, which can be found [here.](https://www.physionet.org/content/apnea-ecg/1.0.0/)

- The dataset contains signals for sleep studied for 35 patients which are labelled by sleep experts. Each 60s window in the signals are labelled with "A" if an apnea event occured or "N" if it is a normal event. 
- 8 of the recordings contain additional signals (a01r, a02r, a03r, a04r, b01r, c01r, c02r, co3r). These additional signals contain chest movements signals, SpO2 signals, etc. These are used for our evaluation
- 60s Segments with Nan or Inf values were discarded.

The general distribution of Apnea and Non-Apnea events:
![data-dist](/plots/apnea_event_distribution.png)

# Model

The model used was a simple CNN model using Conv2D and MaxPool layers, followed by a Fully connected classification head. This was implemented using the keras API of TensorFlow