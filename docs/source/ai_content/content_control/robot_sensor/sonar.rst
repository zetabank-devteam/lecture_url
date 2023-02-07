=====
Sonar
=====

-   02_sonar.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/content_control/sensor2.webp
.. thumbnail:: /_images/content_control/sensor3.webp


.. code-block:: python

    import rospy
    from std_msgs.msg import Float32MultiArray

-   Import the rospy module
-   Import Float32MultiArray from std_msgs.msg module




.. code-block:: python

    def process_sonar(msg):
        rospy.loginfo("data[0]: {},data[1]: {},data[2]: {},data[3]: {}".format(msg.data[0], msg.data[1], msg.data[2], msg.data[3]))

    def start_node():
        rospy.init_node('zetabot')
        rospy.Subscriber("sonar", Float32MultiArray, process_sonar)
        rospy.spin()

    try:
        start_node()
    except rospy.ROSInterruptException as err:
        print(err)


-   Create zetabot Node
-   sonar Topic Subscribe
-   Check message in data array format


.. code-block:: python

    def process_sonar(msg):
        rospy.loginfo("Front: {}, Right: {}, Back: {}, Left: {}".format(msg.data[0], msg.data[1], msg.data[2], msg.data[3]))

    def start_node():
        rospy.init_node('zetabot')
        rospy.Subscriber("sonar", Float32MultiArray, process_sonar)
        rospy.spin()

    try:
        start_node()
    except rospy.ROSInterruptException as err:
        print(err)


-   Create zetabot Node
-   sonar Topic Subscribe
-   Check the message according to the direction

