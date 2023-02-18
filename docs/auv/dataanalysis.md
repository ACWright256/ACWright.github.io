---
layout: page
title: Data Analysis
permalink: /auv/dataanalysis/
exclude: true
---

[Back to project](/auv)

# Data Processing


## Depth Data
<div style="text-align: center">
  <img src="../../assets/img/auv/modelDepthCalibration.png" alt="gpsdeploy" width="800" />
    <img src="../../assets/img/auv/calibratedDataTime.png" alt="gpssat" width="800" />
</div>



## Sonar Data

<div style="text-align: center">
  <img src="../../assets/img/auv/sonarRaw.png" alt="gpsdeploy" width="800" />
  Raw and filtered sonar data for one of the surface measurements in deployment 2. Two strong peaks are visible at 5.4 ms and 23.6 ms, corresponding to reflections at 4 m and 17.7 m


</div>


## GPS Data

<div style="text-align: center">
  <img src="../../assets/img/auv/gpsDeployment3.png" alt="gpsdeploy" width="800" />
    <img src="../../assets/img/auv/satelliteCountDeployment3Time.png" alt="gpssat" width="800" />
</div>
GPS data were inaccurate during deployment when the robot was submerged underwater. This was supported by the model, as testing predicted that the GPS data would be inaccurate if the module becomes obstructed. 
The GPS module was obstructed while the robot was underwater, preventing the robot from reestablishing satellite locks when surfaced. Satellite locks were only able to be reestablished at the end of the deployment when the robot was out of water. Across all deployments, the GPS was unable to lock out of water. Fig. 15 shows the inaccurate GPS data, estimating that the robot had moved 20 m west after the robot submerged underwater, and Fig. 16 shows how the GPS monitor  lost all satellites when underwater.


