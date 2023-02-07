====================
Time Slot Subscriber
====================

-   2_2_타임슬롯_receiver.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/content_control/conv4.png


.. code-block:: python

    2_2_타임슬롯_receiver.ipynb

-   Import rospy modules
-   Import Int32 from std_msgs.msg module


.. code-block:: python

    def callback(msg):
        pass

-   Create callback() function


.. code-block:: python

    rospy.init_node('Receiver')
    sub = rospy.Subscriber('my_topic',Int32, callback)
    rospy.spin()

-   Create Receiver Node
-   Create my_topic Topic Subscriber
