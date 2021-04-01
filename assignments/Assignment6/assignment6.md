# Assignment 6

:o2: author

:o2: proper sections missing

:o2: refernces as footnotes missing

:o2: http links must be encupsulated in `<` `>`

## Training A Vehicle Using Camera Feed from Vehicle Simulation

Making cars self driving has been a pro

## AI Algorithm and Tools

I plan to use the a convolutional neural network to train a neural network that can tune the velocity and steering angle
of a vehicle simulation so that the vechicle will be able to drive itself. The data will come from the CARLA simulator which
uses the driver inputs and puts into a driving log which contains data of the trajectory and the surroundings of the simulated
vehicle. The CARLA simulator uses the the steering angle and throttle to act much like the controllable inputs of a real vehicle.
CARLA is an open-source CARLA has been developed from the ground up to support development, training, and validation of autonomous 
driving systems. In addition to open-source code and protocols, CARLA provides open digital urban layouts, buildings, and vehicles
that were created for this purpose and can be used freely. The simulation platform supports flexible specification of sensor suites,
environmental conditions, full control of all static and dynamic actors, maps generation.

## Open-Source GitHub

To use the CARLA Simulator in google colab we can use the open-souce github below which allows one to use a fully functioning version 
of CARLA, which requires a good GPU. 

<https://github.com/MichaelBosello/carla-colab.git>

## CARLA Simulator
![](CARLA_Image.png)
[^3]

### A link to the CARLA Simulator's website is given below

## References

[^1]:https://github.com/MichaelBosello/carla-colab.git
[^2]:http://carla.org/
[^3]:https://carla.readthedocs.io/en/0.9.7/getting_started/
