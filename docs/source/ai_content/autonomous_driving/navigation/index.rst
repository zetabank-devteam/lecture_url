==============================
Navigation setting for Zetabot
==============================


Mapping In-Action
-----------------

A description of the mapping.


1.  Turn on the Zeta-Bot's power switch.
    
    .. thumbnail:: /_images/autonomous_driving/turnonzeta.jpg

2.  Click the mapping button.
    
    .. thumbnail:: /_images/autonomous_driving/clickmapping.jpg

3.  Try mapping by moving the Zetabot. The part measured in red is the data measured by LIDAR.
    Black is the wall measured by LIDAR through the SLAM algorithm.
    
    .. thumbnail:: /_images/autonomous_driving/mapping.jpg

4.  Control the Zetabot joystick

    .. thumbnail:: /_images/autonomous_driving/controller.png
    
    1. Power button
    2. When the joystick vibrates, it is a signal that the ZetaBot and the joystick are connected.
    3. Press the LB button and use the left joystick to handle and accelerate.
    4. Press the LT button and use the right joystick to rotate the Zetabot.

|
|
|

Navigation In-Action
--------------------

1.  When mapping is finished, click the Navigation button.

    .. thumbnail:: /_images/autonomous_driving/nav_1.jpg

2.  Run localization with 2D Pose Estimate.

    During this stage, it is recommended for LIDAR to have measured the obstacles in green and map them to some extent.

    .. thumbnail:: /_images/autonomous_driving/nav_2.jpg

    .. thumbnail:: /_images/autonomous_driving/nav_3.jpg

3.  If you click 2D Nav Goal to set the target, the settings for autonomous driving is set.

    .. thumbnail:: /_images/autonomous_driving/nav_4.jpg

.. .. toctree:: 
..     :hidden:

..     AI Autonomous Robot 
..     Navigation In-Action