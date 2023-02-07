==========================
Processing Delay Publisher
==========================


-   1_1_처리지연_sender.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/content_control/conv1.png


.. code-block:: python

    import rospy
    from std_msgs.msg import Int32

-   Import rospy modules
-   Import Int32 from std_msgs.msg module



.. code-block:: python

    rospy.init_node('Sender', anonymous=False)
    pub = rospy.Publisher('increase_num', Int32, queue_size=1)
    rate = rospy.Rate(1000) # Generate a topic by incrementing the number by 1 1000 times per second


-   Create Sender Node
-   increase_num Topic Publish
-   Set it to have a rate of 1000hz (1000 executions per second)

.. code-block:: python

    cnt = 1

-   set the variable cnt to 1

.. code-block:: python

    while not rospy.is_shutdown():
        pub.publish(cnt)
        cnt += 1
        rate.sleep()
    rospy.spin()

-   Set to publish cnt Message and increase cnt value by 1 when rospy is running