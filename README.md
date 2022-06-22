# Microsoft_Cybersecurity_Engage_2022
This repository contains code for my solution built as part of Microsoft's Cybersecurity Engage program.

This repository contains simulations of load modulation strategies to optimize instability using Load Frequency Control (LFC) resonant behavior in modern power grids.


Most electricity is produced from electromechanical alternating current generators (driven mainly by heat engines driven by the combustion or fission of the core, but also by other means such as the kinetic energy of the flowing water). The basic feature of generators is that at a constant input of mechanical force they run slower at high loads and faster at low loads. The generated AC frequency is also directly proportional to the machine speed. This is the main cause of the attack presented here. Consider the case where a charge is applied: For aany electromechanical device, the electromagnetic moment or force applied is directly proportional to the current flowing through them. As the charge increases, the current of the generator armature also increases. This armature current in turn creates a magnetic field opposite to the magnetic field, which increases the torque against the shaft and thus reduces the speed (for constant power input).

It is important to keep the frame rate constant at 50 Hz (Europe) or 60 Hz (America and parts of Asia). Charging frequency control is simply a system that adjusts the mechanical input force of the generator to suit the required power and maintain the rated speed, and therefore the electrical frequency.Modern systems are more electronic and can implement advanced control algorithms, but the principle is the same.

Attack Knowing that charge can affect frequency and that there is a system that maintains nominal frequency, another question is what we can do to disrupt that system. This is the response of the system when using a load of 10% of its capacity:

Direct load transfer (20 rad / s) causes the following effect:


Not only is it small, but it is also impossible due to latency. See what happens when the baud rate is 2.27 rad / s (about 3.6 Hz or one cycle every ~ 2.8 seconds):

2.27 Rad / s is the resonant frequency of the system. At this frequency, the maximum rate of change of frequency (ROCOF) is equal to 0.162 p.u. due to the simple application of a charge. (16.2% of plant capacity) - we have effectively increased our load by 62% - and prevented the system from returning to face value permanently. The full deviation, its duration and ROCOF trigger all protection mechanisms that interrupt the power supply in certain areas or completely shut down the network to prevent damage.

The resonant frequency of the system can be seen by running the  ``` Load_Frequency_Control_linear.m``` script and looking at the peak frequency response in the Bode diagram. The system parameters in a given simulation are realistic here and can be found in  ```Load_Frequency_Control_parameter.m``` 
along with other useful calculations.

Instructions for performing the simulation can be found in the Simulink model by opening the DOC blocks. The Power Demand area contains a signal generator for playing various curves. Firewall systems are designed to detect unusual charging requirements patterns - given many classic cyber attacks - but if the attack involves a real load and does not only manipulate sensor data, running firewall protection can be useful because LFC is not appropriate. answer the question about the fee. See also DSM IoT.

# SIMULATION OUTPUT

![sys_single_area](https://user-images.githubusercontent.com/58084673/175018690-6bd1b8f3-25ec-436a-8143-ff731ee415ff.png)
![output](https://user-images.githubusercontent.com/58084673/175018711-2f006292-9a89-4c7e-bfd0-73fcba36f55b.png)
