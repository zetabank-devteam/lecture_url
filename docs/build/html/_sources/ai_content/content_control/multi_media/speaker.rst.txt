=======
Speaker
=======


-   01_sound.ipynb
-   | Running the cell code
    | `Ctrl + Enter`

.. thumbnail:: /_images/content_control/mul1.png


.. code-block:: python

    import rospy
    from std_msgs.msg import Int32MultiArray

-   Import the rospy module
-   Import Int32MultiArray from std_msgs.msg module




.. code-block:: python

    sound = Int32MultiArray()


-   Set sound variable as Int32MultiArray() Message Type

.. code-block:: python

    def play(number):
        sound.data=[1,number]


-   Create play(number) function
-   Specify the data of the sound message in [1,number] format

.. code-block:: python

    def sounds():
        sound_pub = rospy.Publisher('robot_sound',Int32MultiArray, queue_size=1)
        try:
            number = input("0~9 까지 중 골라주세요")
            play(number)
            sound_pub.publish(sound)
            rospy.sleep(2)
        except Exception as ex:
            print(ex)

        
    def start_node():
        rospy.init_node('zetabot')
        while True:
            sounds()
        rospy.spin()
    try:
        start_node()
    except rospy.ROSInterruptException as err:
        print(err)


-   Create the sounds() function
-   Create robot_sound Topic Publisher
-   Get user input into number variable
-   Execute the play(number) function
-   sound Message Publish
-   2 second time delay and exception handling
-   Create start_node() function
-   Create zetabot Node
-   runs the sounds() function
-   start_node() function execution and exception handling