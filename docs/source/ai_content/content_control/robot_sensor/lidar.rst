=====
LIDAR
=====

-   04_scan.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/content_control/sensor5.png


.. code-block:: python

    import rospy
    from sensor_msgs.msg import LaserScan

-   Import the rospy module
-   Import the LaserScan from the sensor_msgs.msg module




.. code-block:: python

    def process_scan(msg):
        rospy.loginfo("data: {}".format(msg))

    def start_node():
        rospy.init_node('zetabot')
        rospy.Subscriber("scan", LaserScan, process_scan)
        rospy.spin()

    try:
        start_node()
    except rospy.ROSInterruptException as err:
        print(err)


-   Create zetabot Node
-   scan Topic Subscribe and Message confirmation
