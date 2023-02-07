==============
Local Cost map
==============

What is Local Cost map?
-----------------------

| If the Global Planner is created while being influenced by the Global Cost Map, the Local Planner is influenced by the Local Cost Map and it creates partial route.
| The important point is that the Local Cost Map is updated in real time based on the data measured by the LIDAR.

|
|
| Next, let's look at the parameters of the Local Cost Map.

| 
|
| **footprint**: This is the contour of the mobile base. In ROS, this is represented by a two-dimensional array of the form [x0, y0], [x1, y1], [x2, y2], ...]. This footprint is used to calculate the radii of the inscribed and circumscribed circles, which are used to inflate the obstacle to fit the robot. In general, to be safe, it's a good idea to define the footprint as slightly larger than the actual contour of the robot. 
| **robot_radius**: If the robot is circular, use it instead of footprint.
| **layer parameters**: Definition of each layer.
|

Obstacle Layer
--------------

| The obstacle layer is responsible for marking and clearing operations. These can be defined in the obstacle layer.

|
| **max_obstacle_height (default: 2.0)**: The maximum height of an obstacle that can be reflected in the costmap. This value should be defined as slightly larger than the robot's height, in meters.
| **obstacle range (default: 2.5)**: This is the distance to be reflected in the costmap. If the distance from the robot is less than the value, it is reflected in the costmap, and the unit is meter. This can be overridden per sensor.
| **raytrace_range (default: 3.0)**: Defines the distance to ray trace an obstacle using sensor data, in meters. This can be overridden per sensor.
| **observation_sources (default: "")**: A list of observation source names separated by spaces. This defines the respective source_name namespace defined below.
| 
|
| Each source_name in observation_sources defines a namespace in which parameters can be defined.

|
| **/source_name/topic (default: source_name)**: The topic of sensor data for this source. Defaults to the name of the source.
| **/source_name/data_type (default: "PointCloud")**: The data type associated with that topic. Currently only "PointCloud," "PointCloud2," and "LaserScan" are supported.
| **/source_name/clearing (default: false)**: Determines whether this observation will be used to clear free space.
| **/source_name/marking (default: true)**: Determines whether this observation will be used to mark obstacles.
| **/source_name/inf_is_valid (default: false)**: Determine whether to receive Inf value in "LaserScan" data message. The Inf value is converted to the maximum value that the laser sensor can measure.
| 
|

Inflation layer
---------------

| The inflation layer sets the inflation of each cell of the obstacle.
| 
| **inflation_radius (default: 0.55)**: The size of the radius by which to inflate the obstacle cost value (in meters).
| **cost_scaling_factor (default: 10.0)**: The scalling factor to apply during dilation.