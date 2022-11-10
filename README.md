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
