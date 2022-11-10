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
1. <b>Image Processing</b> \
We perform data cleaning of the image dataset by iterating through each the given dataset for `normal`, `carrying` and `threat` class. For each class, after applying YOLO, we are able to filter out images without a person inside. The implementation can be found [here](https://github.com/FizzyAgent/cs4243-weapons-detection/blob/master/data_processing/image_processing.ipynb).
2. <b>Audio Processing</b> \
For every video from a class, the extracted mel spectrum from librosa is saved. The implementation can be found [here](https://github.com/FizzyAgent/cs4243-weapons-detection/blob/master/data_processing/image_processing.ipynb).
3. <b>Data Splitting</b> \
We split the dataset such that given a video, if its frames are being used for training, its mel spectrum is also used for training. The same mechanism applies for validation and testing. The implementation can be found [here](https://github.com/FizzyAgent/cs4243-weapons-detection/blob/master/data_processing/dataset_split.ipynb).

### Training
In `training` directory, you can find the scripts for [training for images](https://github.com/FizzyAgent/cs4243-weapons-detection/blob/master/training/image_training.ipynb), [training for audio](https://github.com/FizzyAgent/cs4243-weapons-detection/blob/master/training/spectrogram_training.ipynb) and [ensemble testing](https://github.com/FizzyAgent/cs4243-weapons-detection/blob/master/training/ensemble_testing.ipynb).

### Demo
In `demo` directory, you can find our original video for demo and [the output video with class annotation](https://github.com/FizzyAgent/cs4243-weapons-detection/blob/master/demo/0217442_3182022_threat_1283_output_classification.mp4) in all of its frames.

You can try with other video by changing the `video_name` variable in `demo/demo.ipynb`.
