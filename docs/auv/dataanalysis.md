---
layout: page
title: Data Analysis
permalink: /auv/dataanalysis/
exclude: true
---

[Back to project](/auv)

# Data Processing


## Depth Data
The pressure sensor and amplifier circuit behaved differently than the model, despite calibrating the system in the tank room a couple days prior to deploying at Dana Point. As shown in ||Fig. 12 and Fig. 13,|| during deployment the pressure signal was approximately 1 V higher at a given depth than during tank room testing. This required recalibrating the pressure system at Dana Point. The elevation of the tank room was approximately 390 m above sea level, and Dana Point was at sea level. Air pressure changes by 11.3 Pa/m at low elevations, so Dana Point would be 4.4 kPa higher pressure than Mudd. The model for the amplifier circuit suggests the output at Dana Point would be 0.7 V higher than the tank room output at a given depth. The observed voltage difference was higher than that, so changes in humidity or temperature could also have impacted the measurements, and making manual measurements with the meter stick may have introduced errors into the new calibration curve.


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

<div style="text-align: center">
  <img src="../../assets/img/auv/sonarRaw.png" alt="sonarraw" width="800" />
  Raw and filtered sonar data for one of the surface measurements in deployment 2. Two strong peaks are visible at 5.4 ms and 23.6 ms, corresponding to reflections at 4 m and 17.7 m
</div>


<div style="text-align: center">
  <img src="../../assets/img/auv/sonarRadius.png" alt="sonarrad" width="800" />
  Start and end GPS locations for deployment 2. The circle corresponds to the strong reflection measured around 24 ms in fifteen different sonar samples, suggesting the signal was a reflection from the shore.
</div>




<div style="text-align: center">
  <img src="../../assets/img/auv/d2sonarhist.png" alt="sonarhist" width="800" />
Histogram of 15 deployment 2 reflections that occurred between 15 and 20 m. The average and standard deviation are 17.8 and 1.4 m.
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

The GPS module was obstructed while the robot was underwater, preventing the robot from reestablishing satellite locks when surfaced. Satellite locks were only able to be reestablished at the end of the deployment when the robot was out of water. Across all deployments, the GPS was unable to lock out of water. Fig. 15 shows the inaccurate GPS data, estimating that the robot had moved 20 m west after the robot submerged underwater, and Fig. 16 shows how the GPS monitor  lost all satellites when underwater.


