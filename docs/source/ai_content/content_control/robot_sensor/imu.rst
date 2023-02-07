===
IMU
===

-   01_imu.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/content_control/sensor1.webp


.. code-block:: python

    import rospy
    from sensor_msgs.msg import Imu
    from tf.transformations import quaternion_from_euler

-   Import the rospy module
-   Import Imu from sensor_msgs.msg module
-   Import quaternion_from_euler from tf.transformations module




.. code-block:: python

    def process_imu(msg):
        rospy.loginfo("x: {},y: {},z: {},w: {}".format(msg.orientation.x, msg.orientation.y, msg.orientation.z, msg.orientation.w))

    def start_node():
        rospy.init_node('zetabot')
        rospy.Subscriber("imu", Imu, process_imu)
        rospy.spin()

    try:
        start_node()
    except rospy.ROSInterruptException as err:
        print(err)


-   Create zetabot Node
-   imu Topic Subscribe
-   Check message by dividing it into x, y, z, w values