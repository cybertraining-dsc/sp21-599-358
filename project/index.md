# Project: Training A Vehicle Using Camera Feed from Vehicle Simulation

[![Check Report](https://github.com/cybertraining-dsc/sp21-599-358/workflows/Check%20Report/badge.svg)](https://github.com/cybertraining-dsc/sp21-599-358/actions)
[![Status](https://github.com/cybertraining-dsc/sp21-599-358/workflows/Status/badge.svg)](https://github.com/cybertraining-dsc/sp21-599-358/actions)
Status: in progress, Type: Project

Jesus Badillo, [sp21-599-358](https://github.com/cybertraining-dsc/sp21-599-358/), [Edit](https://github.com/cybertraining-dsc/sp21-599-358/blob/main/project/index.md)

{{% pageinfo %}}

## Abstract

Deep Learning has become the main form of machine learning that has been used to train, test, and gather data for self-driving cars. The CARLA simulator has been developed from the ground up so that reasearchers who normally do not have the capital to generate their own data for self-driving vehicles can do so to fit their spcific model. CARLA provides many tools that can simulate many scenarios that an autonomous vehicle would run into. The benefit of CARLA is that it can simulate scenarios that may be too dangerous for a real vehicle to perform, such as a full self-driving car in a heavly populated area. CARLA has the backing of many companies who lead industry like toyota who invested $100,000 dollars in 2018 [^7]. This project uses the CARLA simulator to visualize how a real camera system based self-driving car sees obstablces and objects.
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

Please not that an up to date version of these instructions is available at

* <https://github.com/cybertraining-dsc/hid-example/blob/main/project/index.md>

Here comes a convincing introduction to the problem

## 2. Using the CARLA Simulator

The CARLA simulator which uses the driver inputs and puts into a driving log which contains data of
the trajectory and the surroundings of the simulated vehicle. The CARLA simulator uses the the steering angle and throttle
to act much like the controllable inputs of a real vehicle. CARLA is an open-source and has been developed from the ground
up to support development, training, and validation of autonomous driving systems. In addition to open-source code and protocols, 
CARLA provides open digital urban layouts, buildings, and vehicles that were created for this purpose and can be used freely.
The simulation platform supports flexible specification of sensor suites, environmental conditions, full control of all static
and dynamic actors, maps generation [^2]. The simulation will be created by driving the vehicle in the simulator and using the
camera feed so that the neural network can be trained. Driving in the simulator looks much like Figure 1.

### Driving in CARLA

![Figure1](https://github.com/cybertraining-dsc/sp21-599-358/raw/main/project/images/CARLA_Image.png)
**Figure 1**
[^3]

## 3. Using the TensorFlow Object Detection API

The Tenserflow object detection API is used to classify objects with a specific level of confidence. Image recognition is useful
for self-driving cars because it can provide known obstacles where the vehicle is prohibited from traveling. The API has been trained
on the COCO dataset which is a dataset consisting of about 300,000 of 90 of the most commonly found objects. Google provided this API to
improve the state of the Computer vision field. Figure2 shows how the bounding boxes classify images using the object detection API. 

### Driving in CARLA

![Figure2](https://github.com/cybertraining-dsc/sp21-599-358/raw/main/project/images/CARLA_Image.png)
**Figure 2**
[^3]

## 4. Implementation

#### System Requirements

This project uses windows 10 along with visual studio code and python 3.7. Note that this project may work with other systems, but CARLA
is a resource intensive program.

|OS Version|GPU|RAM|
|----|----|----|
|Windows 10.0.18363 Build 18363|NVIDIA GTX 1660 Super|32 GB|

In this study the CARLA version 0.9.9 is being used along with python 3.7 to control the vehicle. The vehicle being used in this paper is a
red Tesla Model3 with only one camera sensor.

#### Download for CARLA version 0.9.9
> <https://github.com/carla-simulator/carla/releases/tag/0.9.9
> [^1]

The file to download is shown below:
> CARLA_0.9.9.zip
Make sure to download the compiled version for Windows.


## 5. Deep Learning Algorithm for Self Driving Cars

To train the neural network for the self driving car there will be using a neural network that can learn from its previous iterations much like
q-learning. This class of neural network is called deep Q-Learning and it uses reinforcement learning to map the actions and Q-values transitions
to the input states [^5]. This approach replaces the Q-table from traditional reinforcement learning with neural networks which train the decision
making process of the vehicle.

## 5. Results

> <https://drive.google.com/file/d/13RXIy74APbwSqV_zBs_v59v4ZOnWdtrT/view?usp=sharing
> 
## 5. Benchmark

Your project must include a benchmark. The easiest is to use cloudmesh-common [^2]

## 6. Conclusion

A convincing but not fake conclusion should summarize what the conclusion of the project is.

## 8. Acknowledgments

The author if this project would like to thank Harrison Kinsley from the youtube channel SentDex for providing good resources for how to use deep learning using carla and tensorflow. The author would also like to thank Dr. Gregor von Laszewski for feedback on this report, and Dr. Geoffrey Fox for sharing his knowledge in Deep Learning and Artificial Intelligence throughout this course taught at Indiana University, Bloomington.

## 9. References

[^1]:https://github.com/carla-simulator/carla/releases/tag/0.9.9
[^2]:http://carla.org/
[^3]:https://carla.readthedocs.io/en/0.9.9/getting_started/
[^4]:https://openaccess.thecvf.com/content_cvpr_2018/papers_backup/Mullapudi_HydraNets_Specialized_Dynamic_CVPR_2018_paper.pdf
[^5]:https://towardsdatascience.com/deep-q-learning-tutorial-mindqn-2a4c855abffc
[^6]:https://www.youtube.com/watch?v=EaY5QiZwSP4&t=1595s
[^7]:https://www.tu-auto.com/toyota-invests-in-carla-open-source-av-simulator-project/
[^8]:https://tensorflow-object-detection-api-tutorial.readthedocs.io/en/latest/install.html
[^9]:https://towardsdatascience.com/is-google-tensorflow-object-detection-api-the-easiest-way-to-implement-image-recognition-a8bd1f500ea0
