---
layout: page
title: Data Analysis
permalink: /auv/dataanalysis/
exclude: true
---

[Back to project](/auv)

# Data Processing
In total, there were three deployments

## Depth Data
The pressure sensor and amplifier circuit behaved differently than the model, despite calibrating the system in the tank room a couple days prior to deploying at Dana Point. During deployment, the pressure signal was approximately 1 V higher at a given depth than during tank room testing. This required recalibrating the pressure system at Dana Point. The elevation of the tank room was approximately 390 m above sea level, and Dana Point was at sea level. Air pressure changes by 11.3 Pa/m at low elevations, so Dana Point would be 4.4 kPa higher pressure than Mudd. The model for the amplifier circuit suggests the output at Dana Point would be 0.7 V higher than the tank room output at a given depth. The observed voltage difference was higher than that, so changes in humidity or temperature could also have impacted the measurements, and making manual measurements with the meter stick may have introduced errors into the new calibration curve.


<div style="text-align: center">
  <img src="../../assets/img/auv/finaldepthcal.png.png" alt="depthcal" width="800" />
  Plot of the model (red), and final deployment calibration curve at Dana Point (blue).
</div>

Proper adjustments to the model were made to account for unexpected depth offset from the depth discrepancy. The target depth was changed from 1 m to 0.7 m to prevent the pressure sensor voltage from reaching rail voltage. The final depth resolution of the pressure sensor was 0.8 m. The robot’s calibrated depth during a deployment is shown above.


<div style="text-align: center">
    <img src="../../assets/img/auv/calibratedDataTime.png" alt="depthtime" width="800" />
    Data were collected using the deployment calibration curve. The robot’s target depth was 0.7 m. A combination of steady state error from the P control and ocean current likely affected the robot’s motion.
</div>



## Sonar Data

Multipath interference posed a significant problem during data analysis. Visibility of the initial reflection varied from sample to sample and deployment to deployment. For many sonar samples, it was difficult to discern reflections off the seabed from those off the water surface during the first few milliseconds of data. The beginning of each sample seemed heavily distorted by multipath interference.


One possible explanation for this distortion was reflection from the surface of the water. Because air is less dense than water, less sound will be transmitted to air, and more sound will be reflected. The ratio of reflected and incident amplitudes for a wave traveling between water and air is about 0.9, so the majority of the wave was reflected. 
Multipath interference was less of an issue for further reflections, likely because surface interference was negligible at larger distances.


### Data from Deployment 2
This deployment occurred on the Ocean Institute’s private pier, in the deeper region of Dana Point. Multiple sonar data records were collected at a single location.

<div style="text-align: center">
  <img src="../../assets/img/auv/sonarRaw.png" alt="sonarraw" width="800" />
  Raw and filtered sonar data for one of the surface measurements in deployment 2. Two strong peaks are visible at 5.4 ms and 23.6 ms, corresponding to reflections at 4 m and 17.7 m
</div>

 Many of the sonar data in this deployment featured clear peaks at consistent locations, making it possible to determine the distant objects certain reflections were coming from.The above image shows a reflection most likely off the seafloor at 4 m and a reflection identified as from the shore at 17.7 m.
<div style="text-align: center">

  <img src="../../assets/img/auv/d2sonarhist.png" alt="sonarhist" width="800" />
Histogram of 15 deployment 2 reflections that occurred between 15 and 20 m. The average and standard deviation are 17.8 and 1.4 m.
</div>
 The average and standard deviation of the distance to the shore were determined using 15 sonar datasets which featured a strong reflection between 22 and 26 ms. The reflection was on average 17.8 m away from the robot, with a standard deviation of 1.4 m.

<div style="text-align: center">
  <img src="../../assets/img/auv/sonarRadius.png" alt="sonarrad" width="800" />
  Start and end GPS locations for deployment 2. The circle corresponds to the strong reflection measured around 24 ms in fifteen different sonar samples, suggesting the signal was a reflection from the shore.
</div>

The above image shows a circle of radius 17.8 m centered on the starting GPS position of the robot, confirming that this strong signal was very likely from the shore. The robot traveled to a few different locations during deployment 2, and sonar data were collected from each of these locations, so the standard deviation of 1.4 m was consistent with observed variations in the robot’s distance from the shore.









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


