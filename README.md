# CYBERBAT : Anomaly Detection Using Air Borne Sound

[ SAP Labs : Code with SAP Labs India ] Hackathon : Anomaly Detection Using Air Borne Sound

Refer the problem statement and other specifics here [SAP code](https://sap-code.hackerearth.com/challenges/hackathon/sap-code/custom-tab/anomaly-detection/#Anomaly%20Detection)

[MIMII Dataset: Sound Dataset](https://zenodo.org/record/3384388#.YD52cVkzbCJ) with the detailed explanation.

## Working :

A mesh of network of edge devices like Raspberrypi 4 B with multiple microphones connected to it are deployed across the industrial site.
The sound picked up by the microphones is further analysed and optmised for the detection of the anomoly based on the sound of the machine.
The continuous sound processing is done and sound captured by one microphone will be transferred to the neighbouring nodes in the mesh for federated learning.
We used MFCC for feature extraction and XGBoost for modeling and acheived 100% accuracy for the given dataset MIMII.

## Modeling Overview :

The prediction system is the detection of anomalous sound of industrial machine in an unsupervised manner.
In the training phase only normal operation sounds are being considered and MFCC is used to feature extraction
and XGBoost is used to generate the machine learning model.

## System Architecture :

![img](https://github.com/harshas-repo/cyberbat/blob/main/resources/System%20Architecture.png)

## System Flow Chart :

![img](https://github.com/harshas-repo/cyberbat/blob/main/resources/System%20Flow%20chart.png)

## Machine Learning Overview :

![img](https://github.com/harshas-repo/cyberbat/blob/main/resources/Machine%20Learning%20flowchart.png)

### MFCC :

Mel-frequency cepstral coefficients [(MFCCs)](https://medium.com/prathena/the-dummys-guide-to-mfcc-aceab2450fd) are coefficients that collectively make up an MFC. They are derived from a type of cepstral representation of the audio
clip (a nonlinear "spectrum-of-a-spectrum"). The difference between the cepstrum and the mel-frequency cepstrum is that in the MFC, the frequency bands are equally
spaced on the mel scale, which approximates the human auditory system's response more closely than the linearly-spaced frequency bands used in the normal cepstrum.
This frequency warping can allow for better representation of sound, for example, in audio compression.

### XGBoost :

[XGBoost](https://machinelearningmastery.com/gentle-introduction-xgboost-applied-machine-learning/) is an algorithm that has recently been dominating applied machine learning and Kaggle competitions for structured or tabular data. XGBoost is an implementation of gradient boosted decision trees designed for speed and performance.
In this post you will discover XGBoost and get a gentle introduction to what is, where it came from and how you can learn more.

## MFCC Working :

![img](https://github.com/harshas-repo/cyberbat/blob/main/resources/MFCC.png)

- For balancing false alarm (False positive) and mixed event (False Negative) we are using f1 score for evaluation.

## Wiring For Mono Mic :

- Mic 3V - Pi 3.3v
- Mic Gnd - Pi Gnd
- Mic SEL - Pi Gnd (this is used for channel selection. Connect to 3.3 or GND)
- Mic BCLK - BCM 18 (pin 12)
- Mic LRCL - BCM 19 (pin 35)
- Mic DOUT - BCM 20 (pin 38)

![img](https://github.com/harshas-repo/cyberbat/blob/main/resources/pi%20and%20mic.png)

# Conclusion :

We achieved 100% accurate results for detecting the air borne anomalies in the machinery at an industrial area for the given dataset. And we proposed a mesh network of edge devices
using raspberry pi 4 coupled with microphones. Refer the python [notebook](https://github.com/harshas-repo/cyberbat/blob/main/cyberbat.ipynb) for relevant code and a model is created as .sav or reference.
