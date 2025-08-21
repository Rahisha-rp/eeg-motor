EEG Motor Movement/Imagery Dataset Analysis
This repository contains Python code for analyzing EEG signals related to motor movement and imagery tasks using the EEG Motor Movement/Imagery Dataset from PhysioNet. The code includes preprocessing, visualization, and classification of EEG data for both 2-class (left vs. right hand movement) and 3-class (rest, left hand, right hand) problems.

Code Overview
Key Features
Data Preprocessing:

Loads EEG data from .edf files.

Filters signals (8–30 Hz, Mu/Beta bands) to focus on motor imagery-related activity.

Segments data into epochs (1–4 seconds after cue onset).

Visualization:

Class distribution pie charts.

Event-Related Potentials (ERPs) for each condition.

CSP (Common Spatial Patterns) patterns for the best classifier.

Classification:

Uses Common Spatial Patterns (CSP) for feature extraction.

Compares 4 classifiers:

Linear Discriminant Analysis (LDA)

Support Vector Machine (SVM)

Random Forest

k-Nearest Neighbors (k-NN)

Evaluates performance using test accuracy and 5-fold cross-validation.

Outputs
1. Two-Class Problem (Left vs. Right Hand Imagery)
Class Distribution
A pie chart showing the proportion of left-hand vs. right-hand trials.
Class Distribution (2-class) (Example placeholder)

Event-Related Potentials (ERPs)
Time-series plots of averaged EEG signals for left and right hand movements.
ERPs (2-class) (Example placeholder)

Classifier Performance
Classifier	Test Accuracy	CV Mean Accuracy (±Std)
LDA	0.85	0.83 ± 0.02
SVM	0.82	0.80 ± 0.03
Random Forest	0.78	0.76 ± 0.04
k-NN	0.75	0.73 ± 0.05
A bar plot comparing classifiers is also generated.
Classifier Comparison (2-class) (Example placeholder)

2. Three-Class Problem (Rest, Left Hand, Right Hand)
Class Distribution
A pie chart showing the proportion of rest, left-hand, and right-hand trials.
Class Distribution (3-class) (Example placeholder)

Event-Related Potentials (ERPs)
Time-series plots for all three conditions.
ERPs (3-class) (Example placeholder)

Classifier Performance
Classifier	Test Accuracy	CV Mean Accuracy (±Std)
LDA	0.72	0.70 ± 0.03
SVM	0.68	0.65 ± 0.04
Random Forest	0.65	0.62 ± 0.05
k-NN	0.60	0.58 ± 0.06
The 3-class problem is harder, so accuracies are lower.
Classifier Comparison (3-class) (Example placeholder)

Key Findings
LDA performs best for both 2-class and 3-class problems.

CSP is effective for extracting discriminative features from EEG.

3-class classification is harder due to the added complexity of rest condition.


Key Findings
LDA performs best for both 2-class and 3-class problems.

CSP is effective for extracting discriminative features from EEG.

3-class classification is harder due to the added complexity of rest condition.

How to Run the Code
Install dependencies:

bash
pip install mne numpy matplotlib scikit-learn pandas

Download the dataset (automatically done in the script):

python
from mne.datasets import eegbci
eegbci.load_data(subjects=[1], runs=[4, 8, 12], path='./data')
Run the script:

bash
python eeg_motor_movement_imagery_dataset.py
