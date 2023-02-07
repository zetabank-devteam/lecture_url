===================
Localization & AMCL
===================

What is Localization?
---------------------

.. thumbnail:: /_images/autonomous_driving/localization.webp



| If we made a map earlier, we need to know **where our current location is** so that we can see the map and enjoy the trip.
| Likewise, if the robot has successfully mapped its terrain, it must figure out where it is within the terrain.
| We call the above series of processes **Localization**.

|
|

| Ex)
|

.. thumbnail:: /_images/autonomous_driving/localization_ex.png

When the Rviz of the Zeta bot is launched, press 2D Pose Estimate and adjust the direction, the laser value of the robot and the space of the map match will be shown to some extent.

Localization is the process of estimating where the robot is.

AMCL(Adaptive Monte Carlo Localization)
---------------------------------------

**AMCL** 이란 위의 **Localization** 을 하기 위한 전반적인 알고리즘을 일컫는 말입니다. 
|
You'll see the red arrows in the picture above. These path predictions are called Particles. And the more you move the robot, the closer you can see these particles clustering around the robot. Because the more you move, the more certain you know where you are. The location tracking algorithm used is called AMCL.
|
|
The following describes the parameters that determine the performance of AMCL.

-   **min_particles (default: 100)**: The minimum number of particles to use in the particle filter.
-   **max_particles (default: 5000)**: The maximum number of particles to use in the particle filter.
-   **kld_err (default: 0.01)**: Sets the maximum error between the true and estimated distributions.
-   **update_min_d (default: 0.2)**: The minimum linear distance (in meters) the robot must move to update the filter.
-   **update_min_a (default: π/6.0)**: The minimum angular distance (in radians) the robot must move to update the filter.
-   **resample_interval (default: 2)**: Sets the number of times the particle filter is updated before being resampled.
-   **transform_tolerance (default: 0.1)**: Specifies the amount of time (in seconds) that this transformation will remain valid after being published.
-   **gui_publish_rate (default: -1.0)**: Set how long each scan and path will be displayed for visualization purposes (in hertz) -1.0 disables the feature.