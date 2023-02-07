===================
ROS Topic Publisher
===================


-   01_01_ros_topic_publisher.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/content_control/comm1.webp

.. code-block:: python

    import rospy
    from std_msgs.msg import String
    
-   Importing rospy modules
-   Importing String from std_msgs.msg module

.. code-block:: python

    def talker():
        pub = rospy.Publisher('chatter', String, queue_size=10)
        rospy.init_node('talker', anonymous=True)
        rate = rospy.Rate(10) # 10hz
        while not rospy.is_shutdown():
            hello_str = "hello world %s" % rospy.get_time()
            rospy.loginfo(hello_str)
            pub.publish(hello_str)
            rate.sleep()

-   Create `talker()` function
-   Create talker nodes and chatter topics 
-   Publish "hello world" + ROS Timestamp Message

.. code-block:: python

    try:
        talker()
    except rospy.ROSInterruptException:
        pass

-   Executing the talker() function and handling exceptions