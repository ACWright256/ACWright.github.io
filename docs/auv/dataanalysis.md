---
layout: page
title: Data Analysis
permalink: /auv/dataanalysis/
exclude: true
---

[Back to project](/auv)

# Data Processing


## Depth Data

The pressure sensor amplifier circuit were initially calibrated using the tank room at Harvey Mudd College. During initial testing at Dana Point, the sensor reading was 1 volt higher than expected. The calibration curve was corrected before deployment.



<div style="text-align: center">
  <img src="../../assets/img/auv/finaldepthcal.png.png" alt="depthcal" width="800" />
  Plot of the model (red), and final deployment calibration curve at Dana Point (blue).
</div>

 The target depth was changed from 1 m to 0.7 m to prevent the pressure sensor voltage from reaching rail voltage. The final depth resolution of the pressure sensor was 0.8 m. The robot’s calibrated depth during a deployment is shown above.


<div style="text-align: center">
    <img src="../../assets/img/auv/calibratedDataTime.png" alt="depthtime" width="800" />
    Data were collected using the deployment calibration curve. The robot’s target depth was 0.7 m. A combination of steady state error from the P control and ocean current likely affected the robot’s motion.
</div>



## Sonar Data

Multipath interference posed a significant problem during data analysis. The first few milliseconds of each data record was heavily distorted by multipath interference.


### Data from Deployment 2
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


