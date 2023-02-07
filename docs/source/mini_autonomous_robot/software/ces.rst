====================
CES2023
====================


Simple Maneuverability Instructions for Mini Zetabot
----------------------------------------------------

.. role:: python(code)
    :language: python

-   control.ipynb
-   Running the cell code
    `Ctrl + Enter`

.. thumbnail:: /_images/ai_autonomous_robot/control1.jpg
    :title: 
    
    Control Python ipynb

.. thumbnail:: /_images/ai_autonomous_robot/control2.jpg
    :title: 
    
    Control Python ipynb

-   Jupyter notebook with instructions for Forwards, Backwards, and Rotational movements


.. code-block:: python 

    import rospy
    import json
    from std_msgs.msg import String,  Int32MultiArray
    import time
    import math

-   Import in the necessary python libraries

.. code-block:: python

    move_pub = rospy.Publisher('/robot_command', String, queue_size=1)
    sound = Int32MultiArray()
    sound_pub = rospy.Publisher('robot_sound',Int32MultiArray, queue_size=1)
    rospy.init_node('zetabot', anonymous=True)
    time.sleep(1)

- Initialize zetabot as an object


.. code-block:: python

    def Forward():
        tmp = {"MoveDelta": 0.5}
        msg = json.dumps(tmp)
        rospy.loginfo("Sent: %s", msg)
        sound.data=[1,1,2]
        sound_pub.publish(sound)
        move_pub.publish(msg)

-   Move the robot Forward for delta amount
-   :python:`Forward()`

.. code-block:: python 

    def Backward():
        tmp = {"MoveDelta": -0.5}
        msg = json.dumps(tmp)
        rospy.loginfo("Sent: %s", msg)
        sound.data=[1,0,2]
        sound_pub.publish(sound)
        move_pub.publish(msg)

-   Move the robot Backward for delta amount
-   :python:`Backward()`

.. code-block:: python

    def Rotation():
        tmp = {"TurnDelta": math.radians(180)}
        msg = json.dumps(tmp)
        rospy.loginfo("Sent: %s", msg)
        sound.data=[1,2,2]
        sound_pub.publish(sound)
        move_pub.publish(msg)




-   Rotate the robot with a given radius. (example 180 degrees) 
-   :python:`Rotation()`


.. code-block:: python 

    def stop():
        tmp = {"Stop": 0}
        msg = json.dumps(tmp)
        rospy.loginfo("Sent: %s", msg)
        move_pub.publish(msg)

-   Terminate the movement of the robot
-   :python:`stop()`