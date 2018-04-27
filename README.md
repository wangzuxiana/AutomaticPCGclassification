# AutomaticPCGclassification - Beta version

This repository contains python implementation of one of the systems described in our submission under review:

> Bozkurt, B., Germanakis, I., Stylianou, Y. Automatic classification of heart sounds for heart disease screening, using time-frequency representations and neural networks, Under Review.

This is part of a larger code collection used for running all experiments defined in our submitted manuscript: system with settings: CNN classifier using feature of Sub-band envelopes computed from asyncronous frames extracted with length of 2 seconds and hop size of 1 second. 

The data(~200Mb) is downloaded from Physionet site (https://www.physionet.org/physiobank/database/challenge/2016/) and placed in a data folder created by the script. Physionet data involves train and validation sets. Physionet-validation set is used as the test set. Physionet-train set is splitted to form train and validation sets. Data augmentation is applied to train and validation sets. 

Run the code at your own risk and please cite the publication(citation to be updated upon acceptance) if you use this code in your own work. This repo is not aimed for distributing a well-designed code package but more for quickly sharing part of our code for readers of our manuscript who would like to learn implementation details. 

Dependencies (python packages used): numpy, spectrum, soundfile, keras, tensorflow, matplotlib, scipy, gammatone, resampy. (list of packages in the environment used for testing is available in environmentPackages.txt)

It is suggested that you create a virtual environment, install dependencies. Following that step, to run the experiments, activate your environment, cd to the 'scripts' folder and run in terminal:
$python SingleRepeatedExperiment.py

The script performs 5 random experiments with random splits of train-validation sets (test set is fixed for all experiments). The results are written in data/results folder.

If you would like to simply check results produced for one sample run (5 learning experiments), example resulting files are available in the 'exampleResults' folder including:
- png files: plots of learning curves (acc vs epoch#, loss vs epoch#) and ROC curves
- _res.txt files: contains measures for the system including confusion matrix, sensitivity, specificity, F-measure, etc. 
- other .txt files: log of experiments

