---
layout: page
title: Autonomous Underwater Vehicle
permalink: /auv/
---

<div style="text-align: center">
  <img src="../assets/img/team.png" alt="team" width="800" />
</div>
<n></n>


### Overview
<n></n>
The goal of this project was to create an autonomous underwater vehicle to collect sonar data, GPS data, and depth data for our experimental engineering course. 

### Circuit Design

## Pressure Sensor
<div style="text-align: center">
  <img src="../../assets/schematics/auv/pressure_schem.png" alt="pressuresensor" width="1000" />
</div>
The pressure sensor circuit was designed to amplify the low voltage pressure sensor signal to cover the full bit range of the Teensy's onboard ADC peripheral. The amplifier had a gain of 25, which was determined by the feedback resistor R1 and parallel combination of R2 and R3. Resistors R2 and R3 composed a voltage divider, which created a virtual ground at 0.78 V. The purpose of this virtual ground was to prevent overdriving at atmospheric pressure. 

## Sonar
<div style="text-align: center">
  <img src="../../assets/schematics/auv/sonar_schem.PNG" alt="sonar" width="1000" />
</div>
The sonar system utilized a high-frequency pulse to detect reflections from both the seafloor and distant objects. The speaker produced a 13.8 kHz triangle wave pulse with a pulse width of 500 μs to achieve a high spatial resolution. For paths with a length difference less than 0.75 m, reflected pulses overlapped, causing multipath interference. The high signal frequency ensured that reflections were isolated from low-frequency noise.

The circuit generated a 500 μs triangle wave pulse at 13.8 kHz using a 555 timer triggered by the Teensy. The pulse triggered a voltage-controlled oscillator, which generated a triangle wave amplified by a speaker amplifier with a power of 5 W.  Key components were R8, C7, R11, C11, R17, R18, and C12, which determined the pulse width, frequency, gain, and frequency response of the amplifier. The potentiometer RV1 could be adjusted to change the triangle wave frequency, compensating for component tolerances.

The microphone signal was amplified using a three-stage non-inverting amplifier with an overall gain of 512. Op amps were used to center the signal, and a 1.65 V bias was generated using the remaining op amp and voltage regulator. A high pass Sallen-Key filter was introduced to remove low frequencies, and the output was sampled by the Teensy at 100 kHz, which was sufficient to record the 13.8 kHz signal.


# Mechanical Drawings
<div style="text-align: center">
  <img src="../../assets/schematics/auv/robo_iso.jpg" alt="iso" width="500" />
</div>

<div style="text-align: center">
  <img src="../../assets/schematics/auv/robo_top.jpg" alt="top" width="500" />
</div>

<div style="text-align: center">
  <img src="../../assets/schematics/auv/robo_side.jpg" alt="bottom" width="500" />
</div>


The robot was designed to be compact and hydrodynamic, with a PVC frame equipped with four motors for depth and XY navigation. The center of mass was below the center of buoyancy, and the frame had an open top for easy access to electronics and less GPS interference. A vertically extruding PVC pipe supported the microphone and pressure tube at a standard depth, while the audio exciter was attached to the bottom of the mesh. The robot was made neutrally buoyant by adding pool noodles at the top.
### Deployments
In total, there were three deployments. At each deployment, the robot took multiple GPS, sonar, and pressure data records at the surface and 0.7 meters below the surface.


### Data Processing


## Depth Data

The pressure sensor amplifier circuit were initially calibrated using the tank room at Harvey Mudd College. During initial testing at Dana Point, the sensor reading was 1 volt higher than expected. The calibration curve was corrected before deployment.



<div style="text-align: center">
  <img src="../../assets/img/auv/finaldepthcal.png" alt="depthcal" width="800" />
  Plot of the model (red), and final deployment calibration curve at Dana Point (blue).
</div>

 The target depth was changed from 1 m to 0.7 m to prevent the pressure sensor voltage from reaching rail voltage. The final depth resolution of the pressure sensor was 0.8 m. The robot’s calibrated depth during a deployment is shown above.


<div style="text-align: center">
    <img src="../../assets/img/auv/calibratedDataTime.png" alt="depthtime" width="800" />
    Data were collected using the deployment calibration curve. The robot’s target depth was 0.7 m. A combination of steady state error from the P control and ocean current likely affected the robot’s motion.
</div>



## Sonar Data

Multipath interference posed a significant problem during data analysis. The first few milliseconds of each data record was heavily distorted by multipath interference.


# Data from Deployment 2
This deployment occurred on the Ocean Institute’s private pier, in the deeper region of Dana Point.

<div style="text-align: center">
  <img src="../../assets/img/auv/sonarRaw.png" alt="sonarraw" width="800" />
  Raw and filtered sonar data for one of the surface measurements in deployment 2. Two strong peaks are visible at 5.4 ms and 23.6 ms, corresponding to reflections at 4 m and 17.7 m
</div>

 Many of the sonar data in this deployment featured clear peaks at consistent locations, making it possible to determine the distant objects certain reflections were coming from.The above image shows a reflection most likely off the seafloor at 4 m and a reflection identified as from the shore at 17.7 m.
<div style="text-align: center">

  <img src="../../assets/img/auv/d2sonarhist.png" alt="sonarhist" width="800" />
Histogram of 15 deployment 2 reflections that occurred between 15 and 20 m. The average and standard deviation are 17.8 and 1.4 m.
</div>

<div style="text-align: center">
  <img src="../../assets/img/auv/sonarRadius.png" alt="sonarrad" width="800" />
  Start and end GPS locations for deployment 2. The circle corresponds to the strong reflection measured around 24 ms in fifteen different sonar samples, suggesting the signal was a reflection from the shore.
</div>


## GPS Data

GPS data were inaccurate during deployment when the robot was submerged underwater. This was supported by the model, as testing predicted that the GPS data would be inaccurate if the module becomes obstructed. 
<div style="text-align: center">
  <img src="../../assets/img/auv/gpsDeployment2.png" alt="gpsdeploy" width="800" />
  GPS data recovered during deployment 2. The recorded path starts at the dock, and ends at the shore. The robot’s actual path was confined to the dock.
</div>

<div style="text-align: center">
    <img src="../../assets/img/auv/satelliteCountDeployment2Time.png" alt="gpssat" width="800" />
    Number of locked satellites during deployment 2. No satellites were locked during data collection.

</div>

The GPS module was obstructed while the robot was underwater, preventing the robot from reestablishing satellite locks when surfaced. Satellite locks were only able to be reestablished at the end of the deployment when the robot was out of water. Across all deployments, the GPS was unable to lock out of water.





