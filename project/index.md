# Training A Vehicle Using Camera Feed from Vehicle Simulation

[![Check Report](https://github.com/cybertraining-dsc/sp21-599-358/workflows/Check%20Report/badge.svg)](https://github.com/cybertraining-dsc/sp21-599-358/actions)
[![Status](https://github.com/cybertraining-dsc/sp21-599-358/workflows/Status/badge.svg)](https://github.com/cybertraining-dsc/sp21-599-358/actions)
Status: final, Type: Project

* :o2: Author missing
* :o2: Introduction missing
* :o2: Title missing
* :o2: Abstract should be defined by now
* :o2: Refernces shoudl be defined by now

Jesus Badillo, [sp21-599-358](https://github.com/cybertraining-dsc/sp21-599-358/), [Edit](https://github.com/cybertraining-dsc/sp21-599-358/blob/main/project/index.md)

{{% pageinfo %}}

## Abstract

Her comes a short abstract of the project that summarizes what it is about

Contents

{{< table_of_contents >}}

{{% /pageinfo %}}

**Keywords:** tensorflow, example. 

## 1. Introduction

Please not that an up to date version of these instructions is available at

* <https://github.com/cybertraining-dsc/hid-example/blob/main/project/index.md>

Here comes a convincing introduction to the problem

## 2. Report Format

The report is written in (hugo) markdown and not commonmark. As such some features are not visible in GitHub. You can 
set up hugo on your local computer if you want to see how it renders or commit and wait 10 minutes once your report is 
bound into cybertraining.

It is to be noted that markdown works best if you include an empty line before and after each context change. 
Thus the following is wrong:

```
# This is My Headline
This author does ignore proper markdown while not using empty lines between context changes
1. This is because this author ignors all best practices
```

Instead, this should be 

```
# This is My Headline

We do not ignore proper markdown while using empty lines between context changes

1. This is because we encourage best practices to cause issues.
```

## 2.1. GitHub Actions

When going to GitHub Actions you will see a report is automatically generated with some help on improving your markdown. 
We will not review any document that does not pass this check.

## 2.2. Past Copy from Word or other Editors is a Disaster!

We recommend that you use a proper that is integrated with GitHub or you use the commandline tools. We may include 
comments into your document that you will have to fix, If you guys past copy you will 

1. Not learn how to use GitHub properly and we deduct points
2. Overwrite our coments that you than may miss and may result in point deductions as you have not addressed them.

## 2.3. Report or Project

You have two choices for the final project. 

1. Project, That is a final report that includes code.
2. Report, that is a final project without code.

You will be including the type of the project as a prefix to your title, as well as in the Type tag
at the beginning of your project.

## 3. Using Images

![Figure 1](https://github.com/cybertraining-dsc/fa20-523-314/raw/main/project/images/chart.png)

**Figure 1:** Images can be included in the report, but if they are copied you must cite them [^1].

## 4. Using itemized lists only where needed

Remember this is not a powerpoint presentation, but a report so we recommend

1. Use itemized or enumeration lists sparingly
2. When using bulleted lists use * and not -

## 5. Datasets

Datasets can be huge and GitHub has limited space. Only very small datasets should be stored in GitHub.
However, if the data is publicly available you program must contain a download function instead that you customize.
Write it using pythons `request`. You will get point deductions if you check-in data sets that are large and do not use
the download function.

## 6. Benchmark

Your project must include a benchmark. The easiest is to use cloudmesh-common [^2]
 
## 6. Conclusion

A convincing but not fake conclusion should summarize what the conclusion of the project is.

## 8. Acknowledgments

Please add acknowledgments to all that contributed or helped on this project.

## 9. References

[^1]:https://github.com/MichaelBosello/carla-colab.git
[^2]:http://carla.org/
[^3]:https://carla.readthedocs.io/en/0.9.7/getting_started/
[^4]:https://openaccess.thecvf.com/content_cvpr_2018/papers_backup/Mullapudi_HydraNets_Specialized_Dynamic_CVPR_2018_paper.pdf
[^5]:https://towardsdatascience.com/deep-q-learning-tutorial-mindqn-2a4c855abffc
[^6]:https://www.youtube.com/watch?v=EaY5QiZwSP4&t=1595s

## Training A Vehicle Using Camera Feed from Vehicle Simulation

Making cars self driving has been a problem that many car companies have been trying to tackle in the 21st century.
There are many different approaches that have been used which all involve deep learning. The approaches all train data
that are gathered from a variety of sensors working together. Lidar and computer vision are the main sensors that are
used by commercial companies. Tesla uses video gathered from multiple cameras to train their neural network [^4] which
is known as HydraNet. In this project, a simulation of a real driving vehicle with a camera feed will be used to train
a neural network that will attempt to make the car drive itself. 

## Using the CARLA Simulator

The data will come from the CARLA simulator which uses the driver inputs and puts into a driving log which contains data of
the trajectory and the surroundings of the simulated vehicle. The CARLA simulator uses the the steering angle and throttle
to act much like the controllable inputs of a real vehicle. CARLA is an open-source CARLA has been developed from the ground
up to support development, training, and validation of autonomous driving systems. In addition to open-source code and protocols, 
CARLA provides open digital urban layouts, buildings, and vehicles that were created for this purpose and can be used freely.
The simulation platform supports flexible specification of sensor suites, environmental conditions, full control of all static
and dynamic actors, maps generation [^2]. The data gathered will be created by driving the vehicle in the simulator and using the
camera feed so that the neural network can be trained. The driving in the simulator looks like the image below.

### Driving in CARLA

![](CARLA_Image.png)
[^3]

### Running CARLA in Google Colab

To use the CARLA Simulator in google colab we can use the open-souce github below which allows one to use a fully functioning version 
of CARLA, which requires a good GPU. Note that using this requires one to download TurboVNC and Cloudfared to be able to run CARLA remotely.
The link to the GitHub repository below provides more instructions on how to use this notebook to run CARLA.

> <https://github.com/MichaelBosello/carla-colab.git>
> [^1]
## Deep Learning Algorithm for Self Driving Cars

To train the neural network for the self driving car I will be using a neural network that can learn from its previous iterations much like
q-learning. This class of neural network is called deep Q-Learning and it uses reinforcement learning to map the actions and Q-values transitions
to the input states [^5]. This approach replaces the Q-table from traditional reinforcement learning with neural networks which train the decision
making process of the vehicle.
