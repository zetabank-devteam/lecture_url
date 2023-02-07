=============
Local Planner
=============


What is Local Planner?
----------------------

In Global Planner,
When the overall path calculation is over, the partial path calculation carried out. This is processed by the Local Planner. The Local Planner accepts and processes the data input from the IMU sensor and LIDAR sensor in real time and publishes it.

DWA Local Planner
-----------------

| In general, when using a local planner, an algorithm called DWA Local Planner is used.
| Next, let's look at the parameters of DWA Local Planner.
| 
|

Robot Configuration Parameters
------------------------------

| **/acc_lim_x (default: 2.5)**: Robot's x-direction acceleration limit (meters/s^2)
| **/acc_lim_th (default: 3.2)**: Robot's angular acceleration limit (radians/s^2)
| **/max_trans_vel (default: 0.55)**: Absolute value of the maximum translational velocity of the robot (m/s)
| **/min_trans_vel (default: 0.1)**: Absolute value of the minimum translational velocity of the robot (m/s)
| **/max_vel_x (default: 0.55)**: Robot's maximum speed in the x direction (m/s)
| **/min_vel_x (default: 0.0)**: The robot's minimum speed in the x-direction. Set a negative value to enable backward (m/s)
| **/max_rot_vel (default: 1.0)**: Absolute value of the maximum rotational speed of the robot (rad/s)
| **/min_rot_vel (default: 0.4)**: Absolute value of the minimum rotational speed of the robot (rad/s)
|
|

Goal Tolerance Parameters
-------------------------

| These parameters controls how well the robot arrives at their target.
| 
| **/yaw_goal_tolerance (double, default: 0.05)**: Angular error (rad) between the target position and the robot's actual position
| **/xy_goal_tolerance (double, default: 0.10)**: x,y position error (meter) between the target position and the actual position of the robot
| **/latch_xy_goal_tolerance (bool, default: false)**: If goal_tolerance is latched, when the robot reaches the goal xy position, it rotates even if it is out of goal tolerance.
|
|

Forward Simulation Parameters
-----------------------------

| These parameters controls how well the robot avoids obstacles.
|
| **/sim_time (default: 1.7)**: A simulation calculation over time of that value. For example, setting 2 to that value will calculate the simulation for the next 2 seconds (in seconds).
| **/sim_granularity (default: 0.025)**: Step size between points on a given trajectory, in meters
| **/vx_samples (default: 3)**: the number of samples in x velocity space
| **/vy_samples (default: 10)**: the number of samples in y velocity space
| **/vtheta_samples (default: 20)**: number of samples in theta velocity (angular velocity) space
| 
|

Trajectory Scoring Parameters
-----------------------------

| These parameters controls how close you get to the path.
|
| **/path_distance_bias (default: 32.0)**: Weights that keep the controller close to a given path (global plan)
| **/goal_distance_bias (default: 24.0)**: Weights that promotes the controller to reach the local goal
| **/occdist_scale (default: 0.01)**: Weights that make the controller avoid obstacles