=======================
Global / Local Coastmap
=======================

-   01_costmap_dy_rc.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/autonomous_driving/global.png

.. code-block:: python

    import rospy
    import dynamic_reconfigure.client

-   Import the rospy module
-   Import dynamic_reconfigure.client module

.. code-block:: python

    class Param(object):
        def __init__(self):
            self.timer = rospy.Timer(rospy.Duration(1), self.call_back)
            self.client1 = dynamic_reconfigure.client.Client("/move_base/global_costmap/",timeout=30)
            self.client2 = dynamic_reconfigure.client.Client("/move_base/local_costmap/",timeout=30)

        def call_back(self, timer):
            self.client1.update_configuration({"footprint": [], "robot_radius": 0.2})
            self.client2.update_configuration({"footprint": [], "robot_radius": 0.2})
            self.timer.shutdown()
            rospy.signal_shut down("")

-   Create Param(object) Class
-   Create init(self) function
-   Create ROS timer and designate callback
-   After creating client1, specify global_costmap of move_base Node in dynamic_reconfigure Client
-   After creating client2, specify local_costmap of move_base Node in dynamic_reconfigure Client
-   Create call_back(self, timer) function
-   Update the parameters of client1 to {"footprint": [], "robot_radius": 0.2}
-   Update the parameters of client2 to {"footprint": [], "robot_radius": 0.2}
-   Timer and ROS shutdown

.. code-block:: python

    rospy.init_node('costmap_dy_rc', anonymous=True)
    param = Param()
    rospy.spin()


-   Create costmap_dy_rc Node
-   Assign Param() Class to param variable