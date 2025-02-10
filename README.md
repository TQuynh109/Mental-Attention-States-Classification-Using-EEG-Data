# Mental Attention States Classification Using EEG Data

[PAPER](https://www.sci-hub.yt/10.1016/j.eswa.2019.05.057) | [Data_Kaggle](https://www.kaggle.com/datasets/inancigdem/eeg-data-for-mental-attention-state-detection/data) 

<img src="Docs/Images/EEG_Brain.jpg" width="900px" height="500px">

## Description

This project focuses on developing a model to classify `mental attention states` using EEG (Electro Encephalo Gram) signals. The classified states include:

- **Focused**: This is the inital stage of the experiment, the subject must maintain a high level on the task, stay alert, and actively monitor the simulation screen.
- **Unfocused**: This is an intermediate state, subject is no longer highly focused but still need to mantain a certain level of alertness.
- **Drowsy**: This is a stage where the subject begins to feel faatigued and loses the ability to stay alert.

The primary goal is to build efficient machine learning models to accurately recognize mental states based on features extracted from EEG signals. Clearly distinguishing these states helps in developing effective monitoring and warning systems, especially in fields such as traffic safety, air traffic control, and industrial machinery operation.

More information: [PAPER](https://www.sci-hub.yt/10.1016/j.eswa.2019.05.057)

## Dataset 

The data was collected from **34** experiments on different subjects to monitor mental attenion states using passive EEG. Below are some key characteristics of the dataset:

1. **Device**: Using EMOTIV EEG to record signals from 4 to 17 channels at a sampling rate of 128Hz

2. **Data Structure**: Raw data is stored in Matlab (.mat) files. 

    Dowload data here: [Data_Kaggle](https://www.kaggle.com/datasets/inancigdem/eeg-data-for-mental-attention-state-detection/data)

    ```
    import kagglehub
    path = kagglehub.dataset_download("inancigdem/eeg-data-for-mental-attention-state-detection")
    print("Path to dataset files:", path)
    ``` 

    You can clone this GitHub repository, the dataset appears in in folder **Data**.
    ```
    git clone https://github.com/TQuynh109/Mental-Attention-States-Classification-Using-EEG-Data.git
    cd EEG-Mental-State-Classification
    ```

3. **Experiment**:

    - Data was collected from 5 subjects. Each participant took part in 7 experiments, performing at most one experiment per day. 
    - The first 2 experiments were used for habituation, and the last 5 trials were used for collecting the data.
    - Timeframes:
        * Focused: During the first 0 to 10 minutes.
        * Unfocused: From 10 to 20 minutes.
        * Drowsy: After 20 minutes.

## Requirements

- Python == 3.7 or 3.8
- tensorflow == 2.X (verified working with 2.0 - 2.3, both for CPU and GPU)

To run the EEG classification sample script, you will also need

- mne >= 0.17.1
- scikit-learn >= 0.20.1
- matplotlib >= 2.2.3

You can use `pip` to install libraries.

```
pip install -r requirements.txt
```

## Results

Built a data processing pipeline consisting of:

- EEG data preprocessing (noise filtering, normalization, ICA, feature extraction)
- Training Machine Learning Models (SVM, Random Forest) and Deep Learning Model (Neutral Network) to classify mental states.

**Results**: The model achieved **96.70%** accuracy under experimental conditions.

Future Development Directions:

- Collect more data from a diverse set of subjects to improve accuracy.
- Apply the system in driver monitoring and brainwave-controlled device applications.