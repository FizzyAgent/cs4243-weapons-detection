# Weapons Detection Project

## Problem Statement
Given a video or image dataset, we are required to develop an algorithm to classify between 3 classes:

0. normal (no weapon is seen)
1. carrying (a weapon is being carried)
2. threat (a weapon based on threat can be detected)

## Task Formulation
Given a video for classification, we extract its image and audio data.

For image data, we apply [YOLO v5](https://github.com/ultralytics/yolov5) to extract the cropped bounding boxes of the detected human.

For audio data, we apply [librosa](https://librosa.org/doc/latest/index.html) to extract the mel spectrum.

## Our Implementation
### Data Processing
1. Image Processing \
We perform data cleaning of the image dataset by iterating through each the given dataset for `normal`, `carrying` and `threat` class. For each class, after applying YOLO, we are able to filter out images without a person inside. The implementation can be found [here](https://github.com/FizzyAgent/cs4243-weapons-detection/blob/master/data_processing/image_processing.ipynb).
2. Audio Processing \
For every video from a class, the extracted mel spectrum from librosa is saved. The implementation can be found [here](https://github.com/FizzyAgent/cs4243-weapons-detection/blob/master/data_processing/image_processing.ipynb).
3. Data Splitting \
We split the dataset such that given a video, if its frames are being used for training, its mel spectrum is also used for training. The same mechanism applies for validation and testing. The implementation can be found [here](https://github.com/FizzyAgent/cs4243-weapons-detection/blob/master/data_processing/dataset_split.ipynb).
