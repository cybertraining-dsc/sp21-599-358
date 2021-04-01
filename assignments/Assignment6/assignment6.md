# Assignment 6

:o2: author

:o2: proper sections missing

:o2: refernces as footnotes missing

:o2: http links must be encupsulated in `<` `>`

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
and dynamic actors, maps generation [^4]. The data gathered will be created by driving the vehicle in the simulator and using the
camera feed so that the neural network can be trained. The driving in the simulator looks like the image below.

### Driving in CARLA
![](CARLA_Image.png)
[^3]

## Open-Source GitHub

To use the CARLA Simulator in google colab we can use the open-souce github below which allows one to use a fully functioning version 
of CARLA, which requires a good GPU. 

<https://github.com/MichaelBosello/carla-colab.git>

### A link to the CARLA Simulator's website is given below

## References

[^1]:https://github.com/MichaelBosello/carla-colab.git
[^2]:http://carla.org/
[^3]:https://carla.readthedocs.io/en/0.9.7/getting_started/
[^4]:https://openaccess.thecvf.com/content_cvpr_2018/papers_backup/Mullapudi_HydraNets_Specialized_Dynamic_CVPR_2018_paper.pdf
