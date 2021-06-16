---
date: 2021-03-15
title: "Project: Training A Vehicle Using Camera Feed from Vehicle Simulation"
linkTitle: 
tags: ["project", "ai", "transportation"]
description: "Training A Vehicle Using Camera Feed from Vehicle Simulation"
author: Jesus Badillo
resources:
- src: "**.{png,jpg}"
  title: "Image #:counter"
---


[![Check Report](https://github.com/cybertraining-dsc/sp21-599-358/workflows/Check%20Report/badge.svg)](https://github.com/cybertraining-dsc/sp21-599-358/actions)
[![Status](https://github.com/cybertraining-dsc/sp21-599-358/workflows/Status/badge.svg)](https://github.com/cybertraining-dsc/sp21-599-358/actions)
Status: final, Type: Project

Jesus Badillo, [sp21-599-358](https://github.com/cybertraining-dsc/sp21-599-358/), [Edit](https://github.com/cybertraining-dsc/sp21-599-358/blob/main/project/index.md)

* Code:
  * [tutorialEgo.py](https://github.com/cybertraining-dsc/sp21-599-358/blob/main/project/code/tutorialEgo.py) 

{{% pageinfo %}}

## Abstract

Deep Learning has become the main form of machine learning that has been used to train, test, and gather data for self-driving cars. The CARLA simulator
has been developed from the ground up so that reasearchers who normally do not have the capital to generate their own data for self-driving vehicles
can do so to fit their spcific model. CARLA provides many tools that can simulate many scenarios that an autonomous vehicle would run into. The benefit
of CARLA is that it can simulate scenarios that may be too dangerous for a real vehicle to perform, such as a full self-driving car in a heavly populated
area. CARLA has the backing of many companies who lead industry like Toyota who invested $100,000 dollars in 2018 [^6]. This project uses the CARLA 
simulator to visualize how a real camera system based self-driving car sees obstacles and objects.

Contents

{{< table_of_contents >}}

{{% /pageinfo %}}

**Keywords:** tensorflow, example.

## 1. Introduction

Making cars self driving has been a problem that many car companies have been trying to tackle in the 21st century.
There are many different approaches that have been used which all involve deep learning. The approaches all train data
that are gathered from a variety of sensors working together. Lidar and computer vision are the main sensors that are
used by commercial companies. Tesla uses video gathered from multiple cameras to train their neural network [^4] which
is known as HydraNet. In this project, a simulation of a real driving vehicle with a camera feed will be used to see the
objects that a car would need to see to train the vehicle to be self-driving

## 2. Using the CARLA Simulator

The CARLA simulator which uses the driver inputs and puts into a driving log which contains data of
the trajectory and the surroundings of the simulated vehicle. The CARLA simulator uses the the steering angle and throttle
to act much like the controllable inputs of a real vehicle. CARLA is an open-source and has been developed from the ground
up to support development, training, and validation of autonomous driving systems. In addition to open-source code and protocols, 
CARLA provides open digital urban layouts, buildings, and vehicles that were created for this purpose and can be used freely.
The simulation platform supports flexible specification of sensor suites, environmental conditions, full control of all static
and dynamic actors, maps generation [^2]. The simulation will be created by driving the vehicle in the simulator and using the
camera feed so that the neural network can be trained. Driving in the simulator looks much like Figure 1.

![Figure1](https://github.com/cybertraining-dsc/sp21-599-358/raw/main/project/images/CARLA_Image.png)

**Figure 1** Driving in Carla Simulator [^3]

### 2.1 Existing Work on Carla

The tutorials over Carla from the youtuber SentDex provide a good introduction into projects that could use deep learning to train self-driving cars.
His tutorials provide a good insight into the Carla Environment so that one could perform their own study [^5].

## 3. Using the TensorFlow Object Detection API

The Tenserflow object detection API is used to classify objects with a specific level of confidence. Image recognition is useful
for self-driving cars because it can provide known obstacles where the vehicle is prohibited from traveling. The API has been trained
on the COCO dataset which is a dataset consisting of about 300,000 of 90 of the most commonly found objects. Google provided this API to
improve the state of the Computer vision field. Figure2 shows how the bounding boxes classify images using the object detection API. 

![Figure2](https://github.com/cybertraining-dsc/sp21-599-358/raw/main/project/images/ObjectCars.png)

**Figure 2** Obect Detection for Cars [^9]

## 4. Implementation

### 4.1 System Requirements

This project uses windows 10 along with visual studio code and python 3.7. Note that this project may work with other systems, but CARLA
is a resource intensive program.

|OS Version|GPU|RAM|
|----|----|----|
|Windows 10.0.18363 Build 18363|NVIDIA GTX 1660 Super|32 GB|

In this study the CARLA version 0.9.9 is being used along with python 3.7 to control the simulated vehicle in the CARLA simulator.

### 4.2 Download and Install CARLA

#### Download for CARLA version 0.9.9

> <https://github.com/carla-simulator/carla/releases/tag/0.9.9> [^1]

##### The file to download is shown below:

> CARLA_0.9.9.zip

Make sure to download the compiled version for Windows. The Carla Simulator is around 25GB, so to replicate the study one must have 30-50GB
of free disk space. Once the file is finished downloading, extract the content of the CARLA zip file into the Downloads folder.

### 4.3 Download and Install TensorFlow Object Detection API

#### From the Downloads folder clone the TensorFlow models git

```
git clone https://github.com/tensorflow/models.git
```

Make sure to clone this git repository into the Downloads folder of your windows machine

### 4.4 Download Protobuf

#### The link to the ProtoBuf repository download is shown below

> <https://github.com/protocolbuffers/protobuf/releases/download/v3.16.0/protoc-3.16.0-win64.zip> [^11]

The Tensorflow Object Detection API uses Protobufs to configure model and training parameters. Before the framework can be used,
the Protobuf libraries must be downloaded and compiled [^8]. Make sure that you extract the file to the Downloads folder. To configure
the model within the directory structure run the commands below.

#### Run the pwd command from powershell and get the path from root to Downloads folder

```
pwd
```

#### When running the command make sure that you are in '~/Downloads/models-master/research'

```
'PathFromDownloads/Downloads'/protoc object_detection/protos/*.proto --python_out=.
```

The command shown above configures protobuf so that the object detection API could be used. Make sure you are in the Downloads/models-master/research path.
Run the commands below to install all of the necessary packages to run the object detection API.

#### Make sure that you are in Downloads/models-master/research when running this command

```
cp object_detection/packages/tf2/setup.py .
python -m pip install .
```

After installing the packages test your installation from the Downloads/models-master/research path and run the command below.

#### Test Installation

```
python object_detection/builders/model_builder_tf2_test.py
```

#### Test Success

If the test was successful than you will a result similar to the one showed in Figure 3.

![Figure3](https://github.com/cybertraining-dsc/sp21-599-358/raw/main/project/images/ModelSuccess.png)

**Figure 3**

### 4.5 Running Carla With Object Detection

The directory structure for the CARLA for the project shoud have protobuf, the tensorflow models-master directory, and the CARLA_0.9.9 directory
all in the Downloads folder. To correctly run this project one would need to open two powershell windows and run the CARLA client and the file which
is providid in this git repository called tutorialEgo.py. The two code snippets below show how to both programs

#### Run CARLA Client

```
"your path"\Downloads\CARLA_0.9.9\WindowsNoEditor> .\CarlaUE4.exe
```

#### Run Carla Object Detection Program

```
#Make sure to place the tutorialEgo.py in the examples folder from the downloaded carla folder

"your path"\Downloads\CARLA_0.9.9\WindowsNoEditorPythonAPI\examples> py -3.7 .\tutorialEgo.py
```

## 5. Training Model

|Model Name|Speed|COCO mAP|
|----|----|----|
|ssd_mobilenet_v1_coco|fast|21|
|ssd_inception_v2_coco|fast|24|
|rfcn_resnet101_coco|medium|30|
|faster_rcnn_resnet101_coco|medium|32|
|faster_rcnn_inception_resnet_v2_astrous_coco|slow|37|

To perform the object detection in the Cara simulator this project uses the TensorFlow object detection API. The model uses the COCO dataset
which contains five different models each with a different mean average precision. The mean average precison, or mAP, is the product of precision
and recall on detecting bounding boxes. The higher the mAP score, the more accurate the network is but that slows down the speed of the model [^8].
In this project the ssd_mobilenet_v1_coco model was used because it is the fastest of the 5 models providie for the COCO dataset.

## 6. Results

The accuracy of the model was not very good at detecting other scenery, but it was able to detect the most important obstacles for self-driving cars
such as other vehicles, pedestrians, and traffic signals. The video below shows a simulation in the Carla simulated vehicle with object detection.

![Figure4](https://github.com/cybertraining-dsc/sp21-599-358/raw/main/project/images/ProgramRunning.png)

**Figure 4** Object Detection in CARLA

> <https://drive.google.com/file/d/13RXIy74APbwSqV_zBs_v59v4ZOnWdtrT/view?usp=sharing>

## 7. Benchmark

The benchmark used for this project was the StopWatch function from the cloudmesh package [^10]. The function can see how long a particular section
of code took compared to a different section in the program. In this project the section that took the longest was to setup pedestrian and traffic accross
the simulated city. This makes sense because there are many vehicles and pedestrians that need to be spawned while also pre computing there trajectories.

![Figure5](https://github.com/cybertraining-dsc/sp21-599-358/raw/main/project/images/Benchmark.png)

**Figure 5**

## 8. Conclusion

The ssd_mobilenet_v1_coco model did not perform as well as it could have because it sometimes classified some objects wrong. For example, some 
pedestrians walking produced shadows which the object detection models perceived as ski's. The mean average precision of the model was the lowest
of the models trained by the COCO dataset which played a factor in the accuracy of the model. This caused issues in the vehicle's detection of its
surroundings. Overall, the model was good at classifying the main objects it needs to know to drive safely such as pedestrians and other vehicles.
This project fulfilled its purpose by showcasing that it can use the object detection from the camera feed along with built in collison detector 
to be able to train a self-driving vehicle in CARLA.

## 9. Acknowledgments

The author if this project would like to thank Harrison Kinsley from the youtube channel SentDex for providing good resources for how to use deep learning
using carla and tensorflow. The author would also like to thank Dr. Gregor von Laszewski for feedback on this report, and Dr. Geoffrey Fox for sharing 
his knowledge in Deep Learning and Artificial Intelligence throughout this course taught at Indiana University.

## 9. References

[^1]: Link to the Carla_0.9.9 github, [GitHub] 
      <https://github.com/carla-simulator/carla/releases/tag/0.9.9>

[^2]: Link to Carla website, [Online Resource] 
      <http://carla.org/>

[^3]: Documentation Explaing Key Features of Carla, [Online Resource] 
      <https://carla.readthedocs.io/en/0.9.9/getting_started/>

[^4]: Explains architecture of Tesla's Neural Network,[Online Resource] 
      <https://openaccess.thecvf.com/content_cvpr_2018/papers_backup/Mullapudi_HydraNets_Specialized_Dynamic_CVPR_2018_paper.pdf>

[^5]: Introduction to Carla with Python, [Online Resource] 
      <https://pythonprogramming.net/introduction-self-driving-autonomous-cars-carla-python/>

[^6]: Toyota info on Carla simulator, [Online Resource] 
      <https://www.tu-auto.com/toyota-invests-in-carla-open-source-av-simulator-project/>

[^7]: Tutorial For TensorFlow Object Detection API, [Online Resource] 
      <https://tensorflow-object-detection-api-tutorial.readthedocs.io/en/latest/install.html>

[^8]: Explains differences between models being used for Object Detection and performance, [Online Resource] 
      <https://towardsdatascience.com/is-google-tensorflow-object-detection-api-the-easiest-way-to-implement-image-recognition-a8bd1f500ea0>

[^9]: Object Detection Image, [Online Resource] 
      <https://www.researchgate.net/figure/Object-detection-in-a-dense-scene_fig4_329217107>

[^10]: Gregor von Laszewski, Cloudmesh StopWatch and Benchmark from the Cloudmesh Common Library, [GitHub] 
      <https://github.com/cloudmesh/cloudmesh-common>

[^11]: Protobuf github download, [GitHub]
      <https://github.com/protocolbuffers/protobuf/releases/download/v3.16.0/protoc-3.16.0-win64.zip>
